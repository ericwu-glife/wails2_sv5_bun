<script lang="ts">
import "./app.css";
import svelteLogo from './assets/svelte.svg'
import viteLogo from '/vite.svg'
import Counter from './lib/Counter.svelte'
import Greet from "$lib/Greet.svelte";
import * as Sidebar from "$lib/components/ui/sidebar";
import { Separator } from "$lib/components/ui/separator"
import * as Breadcrumb from "$lib/components/ui/breadcrumb"
import { AppSidebar } from "$lib/ucs";

let active = $state("");
let ActiveUC = $derived.by(() =>{
  switch(active) {
    case "counter":
      return Counter;
    case "greet":
      return Greet;
  }
});
</script>
<Sidebar.Provider>
  <AppSidebar bind:active={active} />
  <Sidebar.Inset class="flex h-screen">
      <header class="flex h-16 shrink-0 items-center gap-2">
          <div class="flex items-center gap-2 px-4">
              <Sidebar.Trigger class="-ml-1" />
              <Separator orientation="vertical" class="mr-2 h-4" />
              <Breadcrumb.Root>
                  <Breadcrumb.List>
                      <Breadcrumb.Item class="block">
                          <Breadcrumb.Link href="#">Application</Breadcrumb.Link>
                      </Breadcrumb.Item>
                      <Breadcrumb.Separator/>
                      <Breadcrumb.Item class="block">
                          <Breadcrumb.Link href="#">{active}</Breadcrumb.Link>
                      </Breadcrumb.Item>
                  </Breadcrumb.List>
              </Breadcrumb.Root>
          </div>
      </header>
      <div class="p-4 pt-0">
        <ActiveUC/>
      </div>
  </Sidebar.Inset>
</Sidebar.Provider>