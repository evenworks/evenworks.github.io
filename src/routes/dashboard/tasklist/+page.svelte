<script lang="ts">
	import * as Sidebar from "$lib/components/ui/sidebar/index.js";
	import * as Breadcrumb from "$lib/components/ui/breadcrumb/index.js";
	import { Separator } from "$lib/components/ui/separator/index.js";
	import { base } from '$app/paths';
</script>

<header
class="flex h-16 shrink-0 items-center gap-2 transition-[width,height] ease-linear group-has-[[data-collapsible=icon]]/sidebar-wrapper:h-12"
>
<div class="flex items-center gap-2 px-4">
	<Sidebar.Trigger class="-ml-1" />
	<Separator orientation="vertical" class="mr-2 h-4" />
	<Breadcrumb.Root>
		<Breadcrumb.List>
			<Breadcrumb.Item class="hidden md:block">
				<Breadcrumb.Link href="{base}/dashboard">Dashboard</Breadcrumb.Link>
			</Breadcrumb.Item>
			<Breadcrumb.Separator class="hidden md:block" />
			<Breadcrumb.Item>
				<Breadcrumb.Page>Tasklist</Breadcrumb.Page>
			</Breadcrumb.Item>
		</Breadcrumb.List>
	</Breadcrumb.Root>
</div>
</header>
<div class="flex flex-1 flex-col gap-4 p-4 pt-0">
    <span>This is tasklist</span>
</div>