<script>
    import { theme } from '$lib/stores';
    
    const themes = [
        { value: 'system', label: 'System' },
        { value: 'light', label: 'Light' },
        { value: 'light-blue', label: 'Light Blue' },
        { value: 'dark', label: 'Dark' },
        { value: 'oled-dark', label: 'OLED Dark' },
        { value: 'her', label: 'Her' }
    ];
    
    function handleThemeChange(newTheme) {
        theme.set(newTheme);
        document.documentElement.className = '';
        document.documentElement.classList.add(newTheme);
    }
</script>

<select 
    bind:value={$theme} 
    on:change={() => handleThemeChange($theme)}
    class="bg-transparent outline-none"
>
    {#each themes as t}
        <option value={t.value}>{t.label}</option>
    {/each}
</select>