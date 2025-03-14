<script lang="ts">
    import * as Sidebar from "$lib/components/ui/sidebar/index";
    import * as lucide from "lucide-svelte"
    
    let { active = $bindable("")} : { active : string } = $props();
</script>
<Sidebar.Root collapsible={"icon"}>
    <Sidebar.Header/>
    <Sidebar.Content>
        <Sidebar.Group>
            <Sidebar.GroupLabel>Application</Sidebar.GroupLabel>
            <Sidebar.GroupContent>
                <Sidebar.Menu>
                    <Sidebar.MenuItem>
                        <Sidebar.MenuButton onclick={() => { active = "counter"}}
                            isActive={ active == "counter" }>
                            <lucide.Heater/>
                            <span>Counter</span>
                        </Sidebar.MenuButton>
                    </Sidebar.MenuItem>
                    <Sidebar.MenuItem>
                        <Sidebar.MenuButton onclick={() =>{ active = "greet"}}
                            isActive={ active == "greet" }>
                            <lucide.FunctionSquare/>
                            <span>Greet</span>
                        </Sidebar.MenuButton>
                    </Sidebar.MenuItem>
                </Sidebar.Menu>
            </Sidebar.GroupContent>
        </Sidebar.Group>
    </Sidebar.Content>
</Sidebar.Root>