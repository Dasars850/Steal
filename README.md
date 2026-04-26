-- Загрузка красивой библиотеки интерфейса
local OrionLib = loadstring(game:HttpGet(('https://githubusercontent.com')))()

-- Создание главного окна
local Window = OrionLib:MakeWindow({
    Name = "My Roblox Scripts", 
    HidePremium = false, 
    SaveConfig = false
})

-- 🔔 Красивое уведомление о загрузке
OrionLib:MakeNotification({
    Name = "Загрузка скрипта...",
    Content = "Подождите, функции активируются.",
    Time = 3
})

-- Создание вкладки
local Tab = Window:MakeTab({
    Name = "Главное",
    PremiumOnly = false
})

-- 1. Кнопка "Бессмертие"
Tab:AddButton({
    Name = "Включить GodMode",
    Callback = function()
        print("GodMode активирован!")
    end
})

-- 2. Кнопка "Проход сквозь стены"
Tab:AddButton({
    Name = "Включить Noclip",
    Callback = function()
        print("Noclip активирован!")
    end
})

-- 3. Ползунок скорости бега
Tab:AddSlider({
    Name = "Скорость бега",
    Min = 16,
    Max = 200,
    Default = 16,
    Increment = 1,
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
    end    
})

-- Запуск интерфейса
OrionLib:Init()
