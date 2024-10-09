<script setup lang="ts">
import { Icon } from "@iconify/vue";
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from "~/components/ui/dropdown-menu";
import {
  CircleUser,
  Home,
  LineChart,
  Package,
  Package2,
  PanelLeft,
  Search,
  ShoppingCart,
  Users2,
} from "lucide-vue-next";
import {
  Breadcrumb,
  BreadcrumbItem,
  BreadcrumbLink,
  BreadcrumbList,
  BreadcrumbPage,
  BreadcrumbSeparator,
} from "~/components/ui/breadcrumb";
import { Button } from "~/components/ui/button";
import { Sheet, SheetContent, SheetTrigger } from "~/components/ui/sheet";
import { Input } from "~/components/ui/input";

const colorMode = useColorMode();
</script>
<template>
  <header
    class="sticky top-0 z-30 flex h-14 items-center gap-4 border-b bg-background px-4 sm:static sm:h-auto sm:border-0 sm:bg-transparent sm:px-6"
  >
    <Sheet>
      <SheetTrigger as-child>
        <Button size="icon" variant="outline" class="sm:hidden">
          <PanelLeft class="h-5 w-5" />
          <span class="sr-only">Toggle Menu</span>
        </Button>
      </SheetTrigger>
      <SheetContent side="left" class="sm:max-w-xs">
        <nav class="grid gap-6 text-lg font-medium">
          <a
            href="#"
            class="group flex h-10 w-10 shrink-0 items-center justify-center gap-2 rounded-full bg-primary text-lg font-semibold text-primary-foreground md:text-base"
          >
            <Package2 class="h-5 w-5 transition-all group-hover:scale-110" />
            <span class="sr-only">Acme Inc</span>
          </a>
          <a
            href="#"
            class="flex items-center gap-4 px-2.5 text-muted-foreground hover:text-foreground"
          >
            <Home class="h-5 w-5" />
            Dashboard
          </a>
          <a
            href="#"
            class="flex items-center gap-4 px-2.5 text-muted-foreground hover:text-foreground"
          >
            <ShoppingCart class="h-5 w-5" />
            Orders
          </a>
          <a href="#" class="flex items-center gap-4 px-2.5 text-foreground">
            <Package class="h-5 w-5" />
            Products
          </a>
          <a
            href="#"
            class="flex items-center gap-4 px-2.5 text-muted-foreground hover:text-foreground"
          >
            <Users2 class="h-5 w-5" />
            Customers
          </a>
          <a
            href="#"
            class="flex items-center gap-4 px-2.5 text-muted-foreground hover:text-foreground"
          >
            <LineChart class="h-5 w-5" />
            Settings
          </a>
        </nav>
      </SheetContent>
    </Sheet>
    <Breadcrumb class="hidden md:flex">
      <BreadcrumbList>
        <BreadcrumbItem>
          <BreadcrumbLink as-child>
            <a href="#">Dashboard</a>
          </BreadcrumbLink>
        </BreadcrumbItem>
        <BreadcrumbSeparator />
        <BreadcrumbItem>
          <BreadcrumbLink as-child>
            <a href="#">Products</a>
          </BreadcrumbLink>
        </BreadcrumbItem>
        <BreadcrumbSeparator />
        <BreadcrumbItem>
          <BreadcrumbPage>All Products</BreadcrumbPage>
        </BreadcrumbItem>
      </BreadcrumbList>
    </Breadcrumb>
    <div class="relative ml-auto flex-1 md:grow-0">
      <Search class="absolute left-2.5 top-2.5 h-4 w-4 text-muted-foreground" />
      <Input
        type="search"
        placeholder="Search..."
        class="w-full rounded-lg bg-background pl-8 md:w-[200px] lg:w-[320px]"
      />
    </div>
    <DropdownMenu>
      <DropdownMenuTrigger as-child>
        <Button variant="outline">
          <Icon
            icon="radix-icons:moon"
            class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
          />
          <Icon
            icon="radix-icons:sun"
            class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
          />
          <span class="sr-only">Toggle theme</span>
        </Button>
      </DropdownMenuTrigger>
      <DropdownMenuContent align="end">
        <DropdownMenuItem @click="colorMode.preference = 'light'">
          Light
        </DropdownMenuItem>
        <DropdownMenuItem @click="colorMode.preference = 'dark'">
          Dark
        </DropdownMenuItem>
        <DropdownMenuItem @click="colorMode.preference = 'system'">
          System
        </DropdownMenuItem>
      </DropdownMenuContent>
    </DropdownMenu>
    <DropdownMenu>
      <DropdownMenuTrigger as-child>
        <Button variant="secondary" size="icon" class="rounded-full">
          <CircleUser class="h-5 w-5" />
          <span class="sr-only">Toggle user menu</span>
        </Button>
      </DropdownMenuTrigger>
      <DropdownMenuContent align="end">
        <DropdownMenuLabel>My Account</DropdownMenuLabel>
        <DropdownMenuSeparator />
        <DropdownMenuItem>Settings</DropdownMenuItem>
        <DropdownMenuItem>Support</DropdownMenuItem>
        <DropdownMenuSeparator />
        <DropdownMenuItem>Logout</DropdownMenuItem>
      </DropdownMenuContent>
    </DropdownMenu>
  </header>
</template>
