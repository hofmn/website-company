<script lang="ts">
    import { AppBar } from '@skeletonlabs/skeleton';
    import { popup } from '@skeletonlabs/skeleton';
    import type { PopupSettings } from '@skeletonlabs/skeleton';
    import { ListBox, ListBoxItem } from '@skeletonlabs/skeleton';
    
    const popupClick: PopupSettings = {
        event: 'click',
        target: 'popupClick',
        placement: 'left',
        middleware: {
            offset: 24
        }
        
    };
    
    let selection: string =''

    function scrollToSection(sectionId: string): void {
        const section = document.getElementById(sectionId);
        if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
        }
  }

</script>

<AppBar>
    <svelte:fragment slot="lead">
        <h3 class="h3">LOGO</h3>
    </svelte:fragment>
    <svelte:fragment slot="trail">
        <button class="md:hidden btn-icon btn-icon-sm variant-ringed-primary" use:popup={popupClick}><i class="fa-solid fa-bars"></i></button>
		
        <div class="card bg-initial p-2" data-popup="popupClick">
            <ListBox>
                <ListBoxItem bind:group={selection} name="small" value='home'>
                    <button class="btn variant-filled-surface"  on:click={() => scrollToSection('home')}>Home</button>
                </ListBoxItem>
                <ListBoxItem bind:group={selection} name="small" value='products' on:click={() => scrollToSection('products')}>
                    <button class="btn variant-filled-surface"  on:click={() => scrollToSection('products')}>Products</button>
                </ListBoxItem>
                <ListBoxItem bind:group={selection} name="small" value='aboutus' >
                    <button class="btn variant-filled-surface"  on:click={() => scrollToSection('aboutus')}>About Us</button>
                </ListBoxItem>
                <ListBoxItem bind:group={selection} name="small" value='contact'>
                    <button class="btn variant-filled-surface" on:click={() => scrollToSection('contact')}>Contact</button>
                </ListBoxItem>
            </ListBox>
        </div>
        <!-- Navbar für größere Geräte -->
        <div class="md:block hidden justify-between">
            <button class="btn bg-primary-300 focus:bg-primary-500"  on:click={() => scrollToSection('home')}>Home</button>
            <button class="btn bg-primary-300 focus:bg-primary-500" on:click={() => scrollToSection('products')}>Products</button>
            <button class="btn bg-primary-300 focus:bg-primary-500" on:click={() => scrollToSection('aboutus')}>About Us</button>
            <button class="btn variant-filled-primary" on:click={() => scrollToSection('contact')}><i class="mx-2 fa-solid fa-envelope"></i>Contact</button>
        </div>

        <a href="#contact" class="md:hidden btn-icon btn-icon-sm variant-filled-primary on:click={() => scrollToSection('contact')}"><i class="fa-solid fa-envelope"></i></a>
    </svelte:fragment>
</AppBar> 