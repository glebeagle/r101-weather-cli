# `wf` (weather forecast)

`wf` - утилита, которая выводит прогноз погоды в терминал, используя [API Яндекс.Погоды](https://yandex.ru/dev/weather/doc/dg/concepts/forecast-info.html).

Запустить:

```bash
$ cargo run -q -- -f
```

> [!WARNING]
> Не забудьте переименовать `.env.example` в `.env` или, в случае кастомного названия файла, использовать:
>
> ```rust
> dotenvy::from_filename(".env.dev")?;
> ```

## Использование

```bash
$ cargo build --release

# теперь переместим нашу утилиту в какую-нибудь дирректорию,
# которая находится в $PATH
# (например, подойдет `/usr/local/bin`)
sudo cp ./target/release/wf /usr/local/bin

# перезапустим терминал - и можно запускать ;)
export YANDEX_WEATHER_API_KEY=<YOUR_KEY>
wf -f
```

## Задание

Добавьте к флагу `-f` количество дней, на которое будет даваться прогноз погоды.

```bash
cargo run -q -- -f 3
```

> [!NOTE]  
> Тут стоит сказать, что у "API Яндекс.Погоды" [тариф](https://yandex.ru/dev/weather/doc/dg/concepts/pricing.html) "Погода на вашем сайте" дает прогноз только на 2 (!) последующих периода. Но вы можете использовать тариф "Тестовый", который будет 30 первых дней бесплатным и давать прогноз уже на 7 дней.
>
> Как альтернативу можно использовать OpenWeatherMap (смотри `public-apis#weather` [GitHub repo](https://github.com/public-apis/public-apis#weather))

_(опционально)_ Улучшите вывод прогноза погоды, например, добавив другие поля или изменив цвет определенных элементов для улучшения восприятия.
