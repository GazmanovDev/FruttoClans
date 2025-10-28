# FruttoClans - Система кланов для Minecraft

## 📋 Описание
FruttoClans - это полнофункциональный плагин системы кланов для Minecraft 1.20.1.

## ✨ Основные возможности

### 🎯 Система прав
- Иерархия прав с настраиваемыми рангами
- Права лидера, офицера и участника
- Гибкая настройка прав через конфигурацию

### 📊 Команды
| Команда | Описание | Права |
|---------|----------|-------|
| `/clan` | Главное меню клана | `clan.command.use` |
| `/clan create <name>` | Создать клан | `clan.command.create` |
| `/clan invite <player>` | Пригласить игрока | `clan.admin.manage_members` |
| `/clan kick <player>` | Исключить игрока | `clan.admin.manage_members` |
| `/clan promote <player> <rank>` | Изменить ранг | `clan.admin.manage_members` |
| `/clan setrank <player> <rank>` | Установить ранг | `clan.admin.manage_members` |
| `/clan leave` | Покинуть клан | `clan.member.leave` |
| `/clan disband` | Расформировать клан | `clan.admin.disband` |
| `/clan top [type]` | Топ кланов | `clan.command.top` |
| `/clan setspawn` | Установить точку дома | `clan.admin.set_home` |
| `/clan home` | Телепорт в дом клана | `clan.command.use` |
| `/clan broadcast <msg>` | Объявление клану | `clan.admin.broadcast` |
| `/clan reload` | Перезагрузка плагина | `clan.command.reload` |
| `/helpme` | Запрос помощи у клана | `clan.command.use` |

### 🔐 Система прав

#### Базовые права
- `clan.command.use` - Доступ к основным функциям
- `clan.command.create` - Создание клана
- `clan.command.top` - Просмотр топов
- `clan.command.reload` - Перезагрузка конфигурации
- `clan.member.leave` - Покинуть клан

#### Права администратора
- `clan.admin.disband` - Удаление клана
- `clan.admin.transfer_leader` - Передача лидерства
- `clan.admin.set_home` - Установка точки дома
- `clan.admin.toggle_pvp` - Управление PvP
- `clan.admin.manage_members` - Управление участниками
- `clan.admin.manage_ranks` - Настройка рангов
- `clan.admin.customize` - Кастомизация клана
- `clan.admin.treasury_manage` - Управление казной
- `clan.admin.broadcast` - Рассылка сообщений

### 📦 Интеграция с PlaceholderAPI

Доступные плейсхолдеры:

| Плейсхолдер | Описание | Пример |
|-------------|----------|--------|
| `%frutto_clan_name%` | Название клана | `Warriors` |
| `%frutto_clan_tag%` | Тег клана с цветом | `[WAR]` |
| `%frutto_clan_icon_id%` | ID иконки ItemsAdder | `itemsadder:clan_icon` |
| `%frutto_clan_member_rank%` | Ранг игрока | `Лидер` |
| `%frutto_clan_leader%` | Имя лидера | `Player123` |
| `%frutto_clan_members_count%` | Количество участников | `15` |
| `%frutto_clan_treasury_diamonds%` | Алмазы в казне | `250` |
| `%frutto_clan_treasury_<ITEM>%` | Количество предмета | `100` |
| `%frutto_clan_is_member%` | Состоит ли в клане | `true/false` |
| `%frutto_clan_color%` | Цвет клана | `&6` |
| `%frutto_clan_formatted_name%` | Название с цветом | `&6Warriors` |
| `%frutto_clan_pvp_enabled%` | Статус PvP | `Включен` |

### 💎 Система казны
- Хранение алмазной руды
- Логирование всех транзакций
- История пополнений и снятий
- Права доступа к управлению казной

## 🛠️ Установка

### Установка
1. Скопируйте JAR файл в папку `plugins/` сервера
2. (Опционально) Установите PlaceholderAPI для использования плейсхолдеров
3. Перезапустите сервер
4. Настройте `config.yml` по необходимости

## ⚙️ Конфигурация

### config.yml

```yaml
database:
  type: sqlite
  filename: clans.db

clan:
  max_members: 20
  min_name_length: 3
  max_name_length: 16
  default_color: "&6"
  default_icon: "itemsadder:default_clan_icon"

treasury:
  enabled: true
  items:
    diamond_ore: true
    deepslate_diamond_ore: true

ranks:
  default:
    leader:
      name: "Лидер"
      permissions:
        - clan.admin.disband
        - clan.admin.manage_members
        # ... и т.д.
    
    officer:
      name: "Офицер"
      permissions:
        - clan.admin.manage_members
    
    member:
      name: "Участник"
      permissions: []

messages:
  prefix: "&8[&6FruttoClans&8]&r "
  clan_created: "&aКлан успешно создан!"
  # ... остальные сообщения
```

## 🔧 Зависимости

- **PlaceholderAPI 2.11.5** - Для плейсхолдеров (опционально)
- **SQLite JDBC 3.44.1** - Драйвер базы данных

## 📄 Лицензия

MIT License

## 👤 Автор

**GazmanovDev**
