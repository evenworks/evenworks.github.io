<script lang="ts" module>
	import AudioWaveform from "lucide-svelte/icons/audio-waveform";
	import BookOpen from "lucide-svelte/icons/book-open";
	import Bot from "lucide-svelte/icons/bot";
	import ChartPie from "lucide-svelte/icons/chart-pie";
	import Command from "lucide-svelte/icons/command";
	import Frame from "lucide-svelte/icons/frame";
	import GalleryVerticalEnd from "lucide-svelte/icons/gallery-vertical-end";
	import Map from "lucide-svelte/icons/map";
	import Settings2 from "lucide-svelte/icons/settings-2";
	import SquareTerminal from "lucide-svelte/icons/square-terminal";
	import CalendarDays from "lucide-svelte/icons/calendar-days";
	import ListTodo from  "lucide-svelte/icons/list-todo";

	// This is sample data.
	const data = {
		user: {
			name: "Dante",
			email: "dante@evenworks.us",
			avatar: "",
		},
		teams: [
			{
				name: "Evenworks",
				logo: Command,
				plan: "Free",
			},
		],
// Dashboard at a glance 
// AI Suggestions (hard-coded)
// Website basics (about us, team, CTA) 
		navMain: [
			{
				title: "Calendar",
				url: "/dashboard",
				icon: CalendarDays,
				items: [
					{
						title: "Duo View",
						url: "/dashboard/duo",
					},
					{
						title: "Build Your Own Schedule",
						url: "/dashboard/byos",
					},
				],
			},
			{
				title: "Tasklist",
				url: "/dashboard/tasklist",
				icon: ListTodo,
			},
			{
				title: "Settings",
				url: "/dashboard",
				icon: Settings2,
				items: [
					{
						title: "General",
						url: "#",
					},
					{
						title: "Team",
						url: "#",
					},
					{
						title: "Billing",
						url: "#",
					},
					{
						title: "Limits",
						url: "#",
					},
				],
			},
		],
		projects: [
			{
				name: "Design Engineering",
				url: "#",
				icon: Frame,
			},
		],
	};
</script>

<script lang="ts">
	import NavMain from "$lib/components/nav-main.svelte";
	import NavProjects from "$lib/components/nav-projects.svelte";
	import NavUser from "$lib/components/nav-user.svelte";
	import TeamSwitcher from "$lib/components/team-switcher.svelte";
	import * as Sidebar from "$lib/components/ui/sidebar/index.js";
	import type { ComponentProps } from "svelte";

	let {
		ref = $bindable(null),
		collapsible = "icon",
		...restProps
	}: ComponentProps<typeof Sidebar.Root> = $props();
</script>

<Sidebar.Root bind:ref {collapsible} {...restProps}>
	<Sidebar.Header>
		<TeamSwitcher teams={data.teams} />
	</Sidebar.Header>
	<Sidebar.Content>
		<NavMain items={data.navMain} />
		<!-- <NavProjects projects={data.projects} /> -->
	</Sidebar.Content>
	<Sidebar.Footer>
		<NavUser user={data.user} />
	</Sidebar.Footer>
	<Sidebar.Rail />
</Sidebar.Root>
