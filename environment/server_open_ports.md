Чтобы открыть порты в Ubuntu, нужно настроить брандмауэр (firewall). Ubuntu использует `ufw` (Uncomplicated Firewall) для управления правилами брандмауэра. Вот как это сделать:

1. **Убедитесь, что `ufw` установлен и активен:**

   ```bash
   sudo apt update
   sudo apt install ufw
   sudo ufw enable
   ```

2. **Открыть порты TCP и UDP:**

   Чтобы открыть конкретный порт для TCP и UDP, выполните следующие команды:

   ```bash
   sudo ufw allow 4242/tcp
   sudo ufw allow 4242/udp
   ```

   Если нужно открыть диапазон портов или все порты, это можно сделать следующим образом:

   Открыть диапазон портов (например, с 1000 по 2000):

   ```bash
   sudo ufw allow 1000:2000/tcp
   sudo ufw allow 1000:2000/udp
   ```

   Открыть все порты TCP:

   ```bash
   sudo ufw allow proto tcp from any to any port any
   ```

   Открыть все порты UDP:

   ```bash
   sudo ufw allow proto udp from any to any port any
   ```

3. **Проверка состояния `ufw`:**

   Чтобы убедиться, что порты успешно открыты, можно проверить статус `ufw`:

   ```bash
   sudo ufw status
   ```

4. **Перезагрузите `ufw`, чтобы применить изменения:**

   В большинстве случаев перезагрузка `ufw` не требуется, но на всякий случай можно выполнить:

   ```bash
   sudo ufw reload
   ```

Эти шаги помогут вам открыть необходимые порты TCP и UDP на Ubuntu.
