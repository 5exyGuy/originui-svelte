<script lang="ts">
	import Button, { buttonVariants } from '$lib/components/ui/button.svelte';
	import Checkbox from '$lib/components/ui/checkbox.svelte';
	import Input from '$lib/components/ui/input.svelte';
	import Label from '$lib/components/ui/label.svelte';

	import * as Dialog from '$lib/components/ui/dialog';
</script>

<Dialog.Root>
	<Dialog.Trigger class={buttonVariants({ variant: 'outline' })}>Sign in</Dialog.Trigger>
	<Dialog.Content>
		<div class="flex flex-col items-center gap-2">
			<div
				class="border-border flex size-11 shrink-0 items-center justify-center rounded-full border"
				aria-hidden="true"
			>
				<svg
					class="stroke-svelte size-6"
					xmlns="http://www.w3.org/2000/svg"
					width="28"
					height="28"
					viewBox="0 0 32 32"
					aria-hidden="true"
				>
					<circle cx="16" cy="16" r="13" fill="none" stroke-width="2" />
					<circle cx="16" cy="16" r="9" fill="none" stroke-width="2" />
				</svg>
			</div>
			<Dialog.Header>
				<Dialog.Title class="sm:text-center">Welcome back</Dialog.Title>
				<Dialog.Description class="sm:text-center">
					Enter your credentials to login to your account.
				</Dialog.Description>
			</Dialog.Header>
		</div>

		<form class="space-y-5">
			<div class="space-y-4">
				<div class="space-y-2">
					<Label for="login-email">Email</Label>
					<Input id="login-email" placeholder="hi@yourcompany.com" type="email" required />
				</div>
				<div class="space-y-2">
					<Label for="login-password">Password</Label>
					<Input id="login-password" placeholder="Enter your password" type="password" required />
				</div>
			</div>
			<div class="flex justify-between gap-2">
				<div class="flex items-center gap-2">
					<Checkbox id="login-remember" />
					<Label for="login-remember" class="text-muted-foreground font-normal">Remember me</Label>
				</div>
				<a class="text-sm underline hover:no-underline" href="#title">Forgot password?</a>
			</div>
			<Button type="button" class="w-full">Sign in</Button>
		</form>

		<div
			class="before:bg-border after:bg-border flex items-center gap-3 before:h-px before:flex-1 after:h-px after:flex-1"
		>
			<span class="text-muted-foreground text-xs">Or</span>
		</div>

		<Button variant="outline">Login with Google</Button>
	</Dialog.Content>
</Dialog.Root>
