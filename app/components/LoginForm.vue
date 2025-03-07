<script setup lang="ts">
import { Button } from '@/components/ui/button'
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
import { Input } from '@/components/ui/input'
import { Label } from '@/components/ui/label'

const testCallback = (user) => {
  console.log(user);
}

</script>

<template>
  <div class="flex flex-col gap-6">
    <Card>
      <CardHeader class="text-center">
        <CardTitle class="text-xl">
          Добро пожаловать
        </CardTitle>
        <!-- <CardDescription>
          Login with your Apple or Google account
        </CardDescription> -->
      </CardHeader>
      <CardContent>
        <TelegramLoginWidget 
          mode="callback"
          telegram-login="onson_mail_bot" 
          @callback="testCallback" 
          requestAccess="write" size="large"
        />
        <form>
          <div class="grid gap-6">
            <div class="flex flex-col gap-4">
              <Button variant="outline" class="w-full">
                <img width="24" src="/assets/telegram.svg" alt="" />
                Войти через Telegram
              </Button>
            </div>
            <div
              class="relative text-center text-sm after:absolute after:inset-0 after:top-1/2 after:z-0 after:flex after:items-center after:border-t after:border-border">
              <span class="relative z-10 bg-background px-2 text-muted-foreground">
                или продолжить с
              </span>
            </div>
            <div class="grid gap-6">
              <div class="grid gap-2">
                <Label html-for="email">Номер телефона</Label>
                <Input id="phone" type="phone" placeholder="+998000000000" required />
              </div>
              <div class="grid gap-2">
                <div class="flex items-center">
                  <Label html-for="password">Пароль</Label>
                  <a href="#" class="ml-auto text-sm underline-offset-4 hover:underline">
                    Забыли пароль?
                  </a>
                </div>
                <Input id="password" type="password" required />
              </div>
              <Button type="submit" class="w-full">
                Авторизоваться
              </Button>
            </div>
            <div class="text-center text-sm">
              У вас нет учетной записи?
              <a href="#" class="underline underline-offset-4">
                Зарегистрироваться
              </a>
            </div>
          </div>
        </form>
      </CardContent>
    </Card>
    <div
      class="text-balance text-center text-xs text-muted-foreground [&_a]:underline [&_a]:underline-offset-4 [&_a]:hover:text-primary  ">
      Нажимая продолжить, вы соглашаетесь с нашими <a href="#">Условиями использования</a>.
      и <a href="#">Политика конфиденциальности</a>.
    </div>
  </div>
</template>
