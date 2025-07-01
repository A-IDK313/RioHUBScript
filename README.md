shared.LoaderTitle = "جارٍ تحميل سكربت المطور ريو";
shared.LoaderKeyFrames = {
    [1] = {
        1,
        20
    },
    [2] = {
        2,
        50
    },
    [3] = {
        3,
        80
    },
    [4] = {
        2,
        100
    }
};
local v2 = {
    LoaderData = {
        Name = shared.LoaderTitle or "A Loader",
        Colors = shared.LoaderColors or {
            Main = Color3.fromRGB(0, 0, 0),
            Topic = Color3.fromRGB(7, 167, 0),
            Title = Color3.fromRGB(7, 167, 0),
            LoaderBackground = Color3.fromRGB(255, 255, 255),
            LoaderSplash = Color3.fromRGB(150, 0, 0)
        }
    },
    Keyframes = shared.LoaderKeyFrames or {
        [1] = {
            1,
            10
        },
        [2] = {
            2,
            30
        },
        [3] = {
            3,
            60
        },
        [4] = {
            2,
            100
        }
    }
};
local v3 = {
    [1] = "",
    [2] = "",
    [3] = "",
    [4] = ""
};
function TweenObject(v178, v179, v180)
    game.TweenService:Create(v178, TweenInfo.new(v179, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut), v180):Play();
end
function CreateObject(v181, v182)
    local v183 = Instance.new(v181);
    local v184;
    for v416, v417 in pairs(v182) do
        if (v416 ~= "Parent") then
            v183[v416] = v417;
        else
            v184 = v417;
        end
    end
    v183.Parent = v184;
    return v183;
end
local function v4(v186, v187)
    local v188 = Instance.new("UICorner");
    v188.CornerRadius = UDim.new(0, v186);
    v188.Parent = v187;
end
local v5 = CreateObject("ScreenGui", {
    Name = "Core",
    Parent = game.CoreGui
});
local v6 = CreateObject("Frame", {
    Name = "Main",
    Parent = v5,
    BackgroundColor3 = v2.LoaderData.Colors.Main,
    BorderSizePixel = 0,
    ClipsDescendants = true,
    Position = UDim2.new(0.5, 0, 0.5, 0),
    AnchorPoint = Vector2.new(0.5, 0.5),
    Size = UDim2.new(0, 0, 0, 0)
});
v4(12, v6);
local v7 = CreateObject("ImageLabel", {
    Name = "UserImage",
    Parent = v6,
    BackgroundTransparency = 1,
    Image = "rbxassetid://95595481924491",
    Position = UDim2.new(0, 15, 0, 10),
    Size = UDim2.new(0, 55, 0, 55)
});
v4(25, v7);
local v8 = CreateObject("TextLabel", {
    Name = "UserName",
    Parent = v6,
    BackgroundTransparency = 1,
    Text = "اهلا بك في السكربت",
    Position = UDim2.new(0, 75, 0, 10),
    Size = UDim2.new(0, 200, 0, 50),
    Font = Enum.Font.GothamBold,
    TextColor3 = v2.LoaderData.Colors.Title,
    TextSize = 14,
    TextXAlignment = Enum.TextXAlignment.Left
});
local v9 = CreateObject("TextLabel", {
    Name = "Top",
    TextTransparency = 1,
    Parent = v6,
    BackgroundColor3 = Color3.fromRGB(255, 255, 255),
    BackgroundTransparency = 1,
    Position = UDim2.new(0, 30, 0, 70),
    Size = UDim2.new(0, 301, 0, 20),
    Font = Enum.Font.Gotham,
    Text = "Loader",
    TextColor3 = v2.LoaderData.Colors.Topic,
    TextSize = 10,
    TextXAlignment = Enum.TextXAlignment.Left
});
local v10 = CreateObject("TextLabel", {
    Name = "Title",
    Parent = v6,
    TextTransparency = 1,
    BackgroundColor3 = Color3.fromRGB(255, 255, 255),
    BackgroundTransparency = 1,
    Position = UDim2.new(0, 30, 0, 90),
    Size = UDim2.new(0, 301, 0, 46),
    Font = Enum.Font.Gotham,
    RichText = true,
    Text = "<b>" .. v2.LoaderData.Name .. "</b>",
    TextColor3 = v2.LoaderData.Colors.Title,
    TextSize = 14,
    TextXAlignment = Enum.TextXAlignment.Left
});
local v11 = CreateObject("Frame", {
    Name = "BG",
    Parent = v6,
    AnchorPoint = Vector2.new(0.5, 0),
    BackgroundTransparency = 1,
    BackgroundColor3 = v2.LoaderData.Colors.LoaderBackground,
    BorderSizePixel = 0,
    Position = UDim2.new(0.5, 0, 0, 70),
    Size = UDim2.new(0.8500000238418579, 0, 0, 24)
});
v4(8, v11);
local v12 = CreateObject("Frame", {
    Name = "Progress",
    Parent = v11,
    BackgroundColor3 = v2.LoaderData.Colors.LoaderSplash,
    BackgroundTransparency = 1,
    BorderSizePixel = 0,
    Size = UDim2.new(0, 0, 0, 24)
});
v4(8, v12);
local v13 = CreateObject("TextLabel", {
    Name = "StepLabel",
    Parent = v6,
    BackgroundTransparency = 1,
    Position = UDim2.new(0.5, 0, 1, - 25),
    Size = UDim2.new(1, - 20, 0, 20),
    Font = Enum.Font.Gotham,
    Text = "",
    TextColor3 = v2.LoaderData.Colors.Topic,
    TextSize = 14,
    TextXAlignment = Enum.TextXAlignment.Center,
    AnchorPoint = Vector2.new(0.5, 0.5)
});
function UpdateStepText(v191)
    v13.Text = v3[v191] or "" ;
end
function UpdatePercentage(v193, v194)
    TweenObject(v12, 0.5, {
        Size = UDim2.new(v193 / 100, 0, 0, 24)
    });
    UpdateStepText(v194);
end
TweenObject(v6, 0.25, {
    Size = UDim2.new(0, 346, 0, 121)
});
wait();
TweenObject(v9, 0.5, {
    TextTransparency = 0
});
TweenObject(v10, 0.5, {
    TextTransparency = 0
});
TweenObject(v11, 0.5, {
    BackgroundTransparency = 0
});
TweenObject(v12, 0.5, {
    BackgroundTransparency = 0
});
for v195, v196 in pairs(v2.Keyframes) do
    wait(v196[1]);
    UpdatePercentage(v196[2], v195);
end
UpdatePercentage(100, 4);
TweenObject(v9, 0.5, {
    TextTransparency = 1
});
TweenObject(v10, 0.5, {
    TextTransparency = 1
});
TweenObject(v11, 0.5, {
    BackgroundTransparency = 1
});
TweenObject(v12, 0.5, {
    BackgroundTransparency = 1
});
wait(0.5);
TweenObject(v6, 0.25, {
    Size = UDim2.new(0, 0, 0, 0)
});
wait(0.25);
v5:Destroy();

local Sound = Instance.new("Sound", game:GetService("SoundService"));
Sound.SoundId = "rbxassetid://75038862482887";
Sound:Play();

game.Players.LocalPlayer.Character.Humanoid.Health = 0
wait(0.1)
game.StarterGui:SetCore("SendNotification", {
    Title = "Rio HUB";
    Text = "تم التفعيل بنجاح"; -- ARAB TEAM
    Duration = 5;
})
game:GetService("ReplicatedStorage").RE["1RPNam1eTex1t"]:FireServer("RolePlayName", "سـكـربـت الـمـطـور ريو")

local args = {
    [1] = "PickingRPNameColor",
    [2] = Color3.fromRGB(7, 167, 0), -- Amarelo
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1RPNam1eColo1r"):FireServer(unpack(args))

local args = {
    [1] = "RolePlayBio",
    [2] ="V0.3"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1RPNam1eTex1t"):FireServer(unpack(args))

local args = {
    [1] = "PickingRPBioColor",
    [2] = Color3.fromRGB(0, 0, 255), -- Blue
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1RPNam1eColo1r"):FireServer(unpack(args))
wait(0.5)
game.StarterGui:SetCore("SendNotification", {
    Title = "لاتنسى تشوف الحقوق";
    Text = "حسابي تيك قريبا.."; -- ARAB TEAM
    Duration = 5;
})

loadstring(game:HttpGet(("https://raw.githubusercontent.com/mhmdsx/ui-TKX/refs/heads/main/ui%20TKX.txt")))()
MakeWindow({
Hub = {
Title = "Rio HUB || V0.3 || Brookhaven RB",
Animation = "سكربت Rio HUB"
},
Key = {
KeySystem = false,
Title = "Key System",
Description = "",
KeyLink = "",
Keys = {"12924"},
Notifi = {
Notifications = true,
CorrectKey = "Running the Script...",
Incorrectkey = "The key is incorrect",
CopyKeyLink = "Copied to Clipboard"
}
}
})

MinimizeButton({
Image = "rbxassetid://95595481924491",
Size = {40, 40},
Color = Color3.fromRGB(10, 10, 10),
Corner = true,
Stroke = true,
StrokeColor = Color3.fromRGB(15, 15, 15)
})

local Main = MakeTab({Name = "الكشف"})
local ESP = loadstring(game:HttpGet("https://kiriot22.com/releases/ESP.lua"))()
ESP:Toggle(true)
ESP.Players = false
ESP.Names = false

local Toggle = AddToggle(Main, {
  Name = "تفعيل الكشف",
  Default = false,
  Callback = function(Value)
    ESP.Players = Value
  end
})

local Toggle = AddToggle(Main, {
  Name = "اسامي الاعبين",
  Default = false,
  Callback = function(Value)
    ESP.Names = Value
  end
})
AddColorPicker(Main, {
  Name = "لون ESP ",
  Default = Color3.fromRGB(255, 255, 0),
  Callback = function(Value)
    ESP.Color = Value
  end
})

local Main = MakeTab({Name = "الاغاني"})
local Paragraph = AddParagraph(Main, {"الرجاء قبل تشغيل الاغنية اعمل ريسيت عن طريق الضغط على الزر ادناه", "bom dia meus manos"})
 AddButton(Main, {
Name = "الريسيت",
Callback = function()
    game.Players.LocalPlayer.Character.Humanoid.Health = 0
end
})
AddSection(Main, {"مـشـغـل الـاغـانـي"})
AddTextBox(Main, {
  Name = "للسياره",
  Default = "",
PlaceholderText = "ادخل الكود",
  ClearText = true,
  Callback = function(Value)
local args1 = {
            [1] = "SkateBoard"
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1NoMoto1rVehicle1s"):FireServer(unpack(args1))
 
        -- Replacing the static value with the input from the textbox
        local args2 = {
            [1] = "PickingScooterMusicText",
            [2] = Value -- Here, we use the textbox value to replace 35935204
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1NoMoto1rVehicle1s"):FireServer(unpack(args2))
        
end 
})
AddTextBox(Main, {
  Name = "للسكوتر",
  Default = "",
  PlaceholderText = "ادخل الكود",
  ClearText = true,
  Callback = function(Value)
local args1 = {
            [1] = "SkateBoard"
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1NoMoto1rVehicle1s"):FireServer(unpack(args1))
 
        -- Replacing the static value with the input from the textbox
        local args2 = {
            [1] = "PickingScooterMusicText",
            [2] = Value -- Here, we use the textbox value to replace 35935204
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1NoMoto1rVehicle1s"):FireServer(unpack(args2))
        
end 
}) 
AddTextBox(Main, {
  Name = "للبيت",
  Default = "",
  PlaceholderText = "ادخل الكود",
  ClearText = true,
  Callback = function(input)
local args = {
            [1] = "PickHouseMusicText",
            [2] = input -- Use the user's input here
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Player1sHous1e"):FireServer(unpack(args))
    end
})
AddTextBox(Main, {
  Name = "بدون جيم باس",
  Default = "",
  PlaceholderText = "ادخل الكود",
  ClearText = true,
  Callback = function(Value)
local args1 = {
            [1] = "SkateBoard"
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1NoMoto1rVehicle1s"):FireServer(unpack(args1))
 
        -- Replacing the static value with the input from the textbox
        local args2 = {
            [1] = "PickingScooterMusicText",
            [2] = Value -- Here, we use the textbox value to replace 35935204
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1NoMoto1rVehicle1s"):FireServer(unpack(args2))
        
end 
})
AddSection(Main, {"قائمة العربي"})

AddButton(Main, {
  Name = "فورتنايت ببجي",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "8671258578"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه في عالم",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "125151253990122"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "حزين",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "135308045"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "الحمدلله",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "7609175072"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "جاء الليل",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "132182002773837"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "السلام عليكم",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "7038667176"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "صدام",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "8273849195"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "ويه ويه",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "1164198099"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "حبيبي شنو في",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "7657178494"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "مصري حب",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "93620598835551"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "عراقي حزين",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "80039364766636"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "دبجه",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "76698985299412"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "ازعاج",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "4776398821"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "ضراط",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "4809574295"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "عود قوي",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "114157294180725"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "عود حزين",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "104085669063530"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "يمني وين الوفاء",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "116150415085902"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})
AddButton(Main, {
  Name = "حزينه",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "132378395114388"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "سعودي حزين",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "99123490695024"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اه ياحلو",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "93620598835551"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "تعال عند. دادي",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "7984027399"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "علي ابو حسن وحسين",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "98224127892587"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه سوريه",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "98640789490482"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "خليجي",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "127593500790634"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "رعب",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "1848748988"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "سبونج بوب",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "2396797933"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه عربيه",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "1836685799"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اوو",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "93123670572331"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "ناني",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "8842446965"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddSection(Main, {"قران كريم"})

AddButton(Main, {
  Name = "قران / 1",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "86911769585232"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "قران / 2",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "133272041755020"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "قران / 3",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "88269497623993"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "قران / 4",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "90593176828958"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "قران / 5",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "1836685929"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "قران / 6",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "4711690175"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "إذآن / قرآن",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "1836685873"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})
AddSection(Main, {"السب"})

AddButton(Main, {
  Name = "صوت اهات",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "8107899910"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "سب / 1",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "8701632845"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "سب / 2",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "671399328"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "سب / 3",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "6536444735"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "سب / 4",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "5849978429"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "سب / 5",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "7942547789"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddSection(Main, {"قائمة الاجنبي بكل انواعه"})

AddButton(Main, {
  Name = "DeathBed",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "76463442516219"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "underMy Skin",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "76145067114930"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Tt - Twice",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "136694442832658"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Black Pink",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "113887644073284"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Rare UnLeak",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "79117388043755"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "I Carti",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "95660636199460"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Fuck Love",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "105663787518318"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "XhDCyeuej",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "127356583789936"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Rare Unleakkk 2",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "118767914595173"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Soulless",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "75806444139457"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Pk Ro paris",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "84543400636750"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Hypperdrop",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "78527071535561"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Drain Lieu",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "73154534382655"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Delicuentir",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "112808748111965"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Mistal Fiscorder",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "73743664006156"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Motagem Dimens",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "75038862482887"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "Sab boy",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "85857498059894"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "urue",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "117088145279665"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "LargR Friees",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "84882252466318"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddSection(Main, {"الفونك"})

AddButton(Main, {
  Name = "فونك بافو بافو",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "106317184644394"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك نادر",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "98677515506006"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "88505573152008"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})
AddButton(Main, {
  Name = "افـخـم فـونـك",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "17647322226"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})



AddButton(Main, {
  Name = "فـونـك غـضـب",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "115859025716354"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})



AddButton(Main, {
  Name = "فـونـك 5×30",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "73966367524216"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})


AddButton(Main, {
  Name = "فـونـك عالـمي",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "76578817848504"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})


AddButton(Main, {
  Name = "فـونـك تـيك تـوك",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "93218265275853"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})



AddButton(Main, {
  Name = "فـونـك مـمتاز",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "102402883551679"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فـونـك روسـي",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "103066073385622"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})


AddButton(Main, {
  Name = "فـونـك بـرازيـل",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "75038862482887"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})


AddButton(Main, {
  Name = "فـونـك هـنـدي",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "91301048841024"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})


AddButton(Main, {
  Name = "فـونـك جـهـنـمي",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "96527800313172"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})


AddButton(Main, {
  Name = "فـونـك اسـطوري",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "115028690484951"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})



AddButton(Main, {
  Name = "فـونـك الـتربيـة السيـئة",
  Callback = function()
    	local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "91161894069716"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})
AddButton(Main, {
  Name = "فينوم فونك",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "8086734311"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك نادر",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "4806290024"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})


AddButton(Main, {
  Name = "فونك برازيلي / 1",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "15689446096"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك برازيلي / 2",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "111281710445018"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فةنك دبجه",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "87968531262747"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك ايضاً",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "17422156627"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك دبجه عربي",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "87968531262747"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فوك ذس اس ثانكس",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "9058205566"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "برازيلي",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "111281710445018"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك ناررر",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "73966367524216"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "14145626412"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك حزين",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "16662831858"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "فونك روسي",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "15689441943"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنية فونك / 1",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "15689443663"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 2",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "16190782181"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 3",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "15689448519"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 4",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "7825702538"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك نادره / 5",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "71517955953236"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 6",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "127084858692372"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 7",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "104541292443133"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 8",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "130607529536925"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 9",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "84733736048142"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 10",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "82680101995105"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 11",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "76603092488414"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 12",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "124958445624871"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 13",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "16662833837"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

AddButton(Main, {
  Name = "اغنيه فونك / 14",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "90698302380427"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})
AddSection(Main, {"اصوات ميمز"})
AddButton(Main, {
  Name = "ميمز / 1",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "7341213035"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})
AddButton(Main, {
  Name = "ميمز / 2",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "6389463761"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})
AddButton(Main, {
  Name = "ميمز / 3",
  Callback = function()
     local args = {
    [1] = "SkateBoard"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
local args = {
    [1] = "PickingScooterMusicText",
    [2] = "3007579524"
}
 
game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
  end
})

local Main = MakeTab({Name = "الرحمة"})
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")

local function fetchPlayerNames()
    local namesList = {}
    for _, plr in ipairs(Players:GetPlayers()) do
        if plr ~= Players.LocalPlayer then 
            table.insert(namesList, plr.Name)
        end
    end
    return namesList
end

AddDropdown(Main, {
    Name = "اختر الضحية",
    Default = "...",
    Options = fetchPlayerNames(),
    Callback = function(Value)
        if Value ~= "" then
            getgenv().selectedPlayer = Value
        end
    end
})

local function createBangToggle(name, yOffset, faceBang)
    local bangActive = false
    local connection
    local togglePosition = false

    AddToggle(Main, {
        Name = name,
        Default = false,
        Callback = function(Value)
            bangActive = Value

            local player = Players.LocalPlayer
            local char = player.Character
            if not char then return end

            local humanoid = char:FindFirstChildOfClass("Humanoid")
            if not humanoid then return end

            if Value then
                humanoid.PlatformStand = true

                if connection then connection:Disconnect() end

                connection = RunService.Heartbeat:Connect(function()
                    if bangActive and getgenv().selectedPlayer then
                        local targetPlayer = Players:FindFirstChild(getgenv().selectedPlayer)
                        if targetPlayer and targetPlayer.Character and targetPlayer.Character.PrimaryPart then
                            local targetHead = targetPlayer.Character:FindFirstChild("Head")
                            if targetHead and char.PrimaryPart then
                                local offset = togglePosition and 1 or 4
                                if faceBang then
                                    char:SetPrimaryPartCFrame(targetHead.CFrame * CFrame.new(0, 1, -offset) * CFrame.Angles(0, math.rad(180), 0))
                                else
                                    char:SetPrimaryPartCFrame(targetHead.CFrame * CFrame.new(0, yOffset, offset) * CFrame.Angles(0, 0, 0))
                                end
                                togglePosition = not togglePosition
                                wait(1)
                            end
                        end
                    end
                end)
            else
                humanoid.PlatformStand = false
                if connection then
                    connection:Disconnect()
                    connection = nil
                end
            end
        end    
    })
end

createBangToggle("البانج / 1", -1, false)
createBangToggle("البانج / 2", -1.5, false)
createBangToggle("بانج الوجه / 1", 1, true)
createBangToggle("بانج الوجه / 2", 1, true)

local Main = MakeTab({Name = "الحماية"})
AddButton(Main, {
  Name = "سكربت يقتل الناس بالقنفة",
  Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/0Ben1/fe./main/Fling%20GUI"))()
  end
})

AddButton(Main, {
  Name = "سكربت يطير او يقتل اي احد يطيرك",
  Callback = function()
loadstring(game:HttpGet("https://scriptblox.com/raw/Universal-Script-FE-Fling-GUI-10927"))()
  end
})

AddButton(Main, {
  Name = "سكربت محد يكدر يطيرك",
  Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/zephyr10101/ignore-touchinterests/main/main",true))() 
  end
})

local Main = MakeTab({Name = "اللاعب"})
AddTextBox(Main, {
  Name = "السرعه",
  Default = "",
  PlaceholderText = "ادخـل الـرقـم",
  ClearText = true,
  Callback = function(value)
game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = value     
 end
})
AddTextBox(Main, {
  Name = "القفز",
  Default = "",
  PlaceholderText = "ادخـل الـرقـم",
  ClearText = true,
  Callback = function(value)
game.Players.LocalPlayer.Character.Humanoid.JumpPower = value    
  end
})
AddTextBox(Main, {
  Name = "بعد الشاشه",
  Default = "",
  PlaceholderText = "ادخـل الـرقـم",
  ClearText = true,
  Callback = function(value)
local FovNumber = value
local Camera = workspace.CurrentCamera
Camera.FieldOfView = FovNumber  
  end
})
AddTextBox(Main, {
  Name = "الدوران",
  Default = "",
  PlaceholderText = "ادخـل الرقم",
  ClearText = true,
  Callback = function(Value)
    getgenv().Spinspeed = Value

local Spin = Instance.new'BodyAngularVelocity'
Spin.Parent = game:GetService'Players'.LocalPlayer.Character:FindFirstChild'HumanoidRootPart'
Spin.MaxTorque = Vector3.new(0, math.huge, 100)
wait(0.1)
Spin.AngularVelocity = Vector3.new(100,Spinspeed,0)
  end
})

function MakeNotifi(notification)
    game.StarterGui:SetCore("SendNotification", {
        Title = notification.Title;
        Text = notification.Text;
        Duration = notification.Time;
    })
end

-- Variáveis e funções para a visualização dos jogadores
local viewEnabled = false
local selectedViewPlayer = nil
local characterAddedConnection = nil

local function toggleView(enabled)
    if enabled then
        if selectedViewPlayer then
            local player = selectedViewPlayer
            if player then
                game.Workspace.CurrentCamera.CameraSubject = player.Character
                if characterAddedConnection then
                    characterAddedConnection:Disconnect()
                end
                characterAddedConnection = player.CharacterAdded:Connect(function(character)
                    game.Workspace.CurrentCamera.CameraSubject = character
                end)
                MakeNotifi({
                    Title = "Visualizando " .. player.Name,
                    Text = "Você está visualizando o jogador: " .. player.Name,
                    Time = 6
                })
            else
                print("Jogador não encontrado.")
                viewEnabled = false
            end
        else
            print("Nenhum jogador selecionado para a visualização.")
            viewEnabled = false
        end
    else
        if characterAddedConnection then
            characterAddedConnection:Disconnect()
            characterAddedConnection = nil
        end
        game.Workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character
    end
end

local value = "" -- Variável para armazenar o nome digitado

local function findPlayerByPartialNameOrNickname(partialName)
    value = partialName -- Atualiza a variável com o nome digitado completo
    for _, player in ipairs(game.Players:GetPlayers()) do
        if player.Name:lower():find(partialName:lower(), 1, true) or (player.DisplayName and player.DisplayName:lower():find(partialName:lower(), 1, true)) then
            return player
        end
    end
    return nil
end


-- Conectando eventos de jogador removido
game.Players.PlayerRemoving:Connect(function(player)
    if selectedViewPlayer == player then
        selectedViewPlayer = nil
        if viewEnabled then
            toggleView(false)
            MakeNotifi({
                Title = "Jogador Saiu",
                Text = player.Name .. " saiu do jogo. Visualização desativada.",
                Time = 5
            })
        end
    end
end)

-- Função para manter a câmera no jogador selecionado
local function maintainView()
    while wait() do
        if viewEnabled and selectedViewPlayer then
            local player = selectedViewPlayer
            if player and game.Workspace.CurrentCamera.CameraSubject ~= player.Character then
                game.Workspace.CurrentCamera.CameraSubject = player.Character
            end
        end
    end
end


-- Variável para controlar o estado do Noclip
local noclipEnabled = false
local runService = game:GetService("RunService")

-- Função para definir CanCollide para todas as partes do personagem
local function setCharacterCanCollide(character, canCollide)
    for _, part in ipairs(character:GetDescendants()) do
        if part:IsA("BasePart") then
            part.CanCollide = canCollide
        end
    end
end

-- Função de callback para o botão de alternância de Noclip
local function onNoclipToggle(value)
    noclipEnabled = value
    print("Noclip Enabled:", noclipEnabled)
    
    local player = game.Players.LocalPlayer
    local character = player.Character

    if noclipEnabled then
        -- Inicia um loop para continuamente definir CanCollide
        noclipLoop = runService.Stepped:Connect(function()
            if character then
                setCharacterCanCollide(character, false)
            end
        end)
    else
        -- Desativa o loop e restaura CanCollide
        if noclipLoop then
            noclipLoop:Disconnect()
        end
        if character then
            setCharacterCanCollide(character, true)
        end
    end
end

-- Adiciona o botão de alternância "Noclip"
local Toggle = AddToggle(Main, {
    Name = "اختراق الحائط",
    Default = false,
    Callback = onNoclipToggle
})

AddSection(Main, {"اختراق الاعبين"})

local function getPlayerNames()
    local playerNames = {}
    for _, player in ipairs(game.Players:GetPlayers()) do
        table.insert(playerNames, player.Name)
    end
    return playerNames
end

-- Store selected player for later use
local selectedPlayer = nil
local followHead = false
local connection = nil

-- Function to spectate the selected player
local function spectatePlayer(enable)
    local player = game.Players.LocalPlayer
    local camera = workspace.CurrentCamera

    if selectedPlayer then
        local targetPlayer = game.Players:FindFirstChild(selectedPlayer)
        if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("HumanoidRootPart") then
            if enable then
                -- Set camera to follow the selected player
                camera.CameraSubject = targetPlayer.Character.Humanoid
            else
                -- Reset camera to default (back to the local player)
                camera.CameraSubject = player.Character.Humanoid
            end
        else
            print("Selected player not available or out of game.")
        end
    else
        print("No player selected!")
    end
end

-- Function to float just above the selected player's head without falling
local function floatAbovePlayerHead()
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()

    if character and character:FindFirstChild("HumanoidRootPart") then
        local humanoidRootPart = character.HumanoidRootPart

        if selectedPlayer then
            local targetPlayer = game.Players:FindFirstChild(selectedPlayer)

            if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("Head") then
                local targetHead = targetPlayer.Character.Head

                -- Position above the selected player's head
                humanoidRootPart.CFrame = targetHead.CFrame * CFrame.new(0, 3, 0)

                -- Keep updating the position every frame
                connection = game:GetService("RunService").Heartbeat:Connect(function()
                    if followHead and targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("Head") then
                        -- Update to stay above the player's head
                        humanoidRootPart.CFrame = targetPlayer.Character.Head.CFrame * CFrame.new(0, 3, 0)
                    else
                        connection:Disconnect() -- Disconnect if the toggle is off
                    end
                end)
            else
                print("Target player not found or not in the game.")
            end
        else
            print("No player selected!")
        end
    end
end

-- Function to trigger the secondary script
local function triggerCharacterSizeDown()
    local args = {
        [1] = "CharacterSizeDown",
        [2] = 2.4
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
end

-- Function to teleport behind the selected player and return after 1.5 seconds
local function moveBehindAndReturn()
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")

    if humanoidRootPart and selectedPlayer then
        local targetPlayer = game.Players:FindFirstChild(selectedPlayer)
        if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("HumanoidRootPart") then
            local targetHumanoidRootPart = targetPlayer.Character.HumanoidRootPart

            -- Store the original position
            local originalPosition = humanoidRootPart.CFrame

            -- Move behind the selected player
            humanoidRootPart.CFrame = targetHumanoidRootPart.CFrame * CFrame.new(0, 0, 3)

            -- Wait for 1.5 seconds before returning
            wait(1.5)

            -- Return to original position
            humanoidRootPart.CFrame = originalPosition
        else
            print("Selected player not found or not in the game.")
        end
    else
        print("No player or HumanoidRootPart found!")
    end
end

-- Create the dropdown with player names
AddDropdown(Main, {
    Name = "اختار الاعب",
    Default = "",
    Options = getPlayerNames(),
    Callback = function(value)
        selectedPlayer = value
        print("Player selected: " .. value)
    end    
})

AddButton(Main, {
    Name = "تحديث القائمة",
    Callback = function()
        UMupdatePlayerList()
    end    
})

local flingToggle

-- Add a toggle that allows the player to spectate the selected player
AddToggle(Main, {
    Name = "شوف الاعب",
    Default = false,
    Callback = function(value)
        spectatePlayer(value)
    end    
})

-- Add a button to teleport to the selected player
AddButton(Main, {
    Name = "اذهب الى الاعب",
    Callback = function()
        floatAbovePlayerHead()
    end    
})

local Main = MakeTab({Name = "التنقل"})
AddSection(Main, {"التنقلات"})
AddButton(Main, {
    Name = "لوحة 1",
    Callback = function()
        local plr = game.Players.LocalPlayer
        local char = plr.Character
        local hrp = char:FindFirstChild("HumanoidRootPart")

        if hrp then
            hrp.CFrame = CFrame.new(-242.68215942382812, 89.68680572509766, -549.6495361328125)
        else
            warn("HumanoidRootPart not found")
        end
    end
})

AddButton(Main, {
    Name = "لوحة 2",
    Callback = function()
        local plr = game.Players.LocalPlayer
        local char = plr.Character
        local hrp = char:FindFirstChild("HumanoidRootPart")

        if hrp then
            hrp.CFrame = CFrame.new(-630.480712890625, 26.586822509765625, 365.14093017578125)
        else
            warn("HumanoidRootPart not found")
        end
    end
})

-- Function to teleport to Teleport
local function teleportToGasStation()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(192, 4, 272)
end

AddButton(Main, {
    Name = "ورا البيوت",
    Description = "",
    Callback = teleportToGasStation
})

-- Function to teleport to Teleport
local function teleportToCenter()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(136, 4, 117)
end

AddButton(Main, {
    Name = "قدام البيوت",
    Description = "",
    Callback = teleportToCenter
})

-- Function to teleport to Criminal
local function teleportToCriminal()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-119, -28, 235)
end

AddButton(Main, {
    Name = "مكان أسلحة",
    Description = "Teleporta para as coordenadas do Criminal",
    Callback = teleportToCriminal
})

-- Function to teleport to House Abandoned
local function teleportToHouseAbandoned()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(986, 4, 63)
end

AddButton(Main, {
    Name = "البيت الفقير",
    Description = "Teleporta para as coordenadas da Casa Abandonada",
    Callback = teleportToHouseAbandoned
})

-- Function to teleport to Portal Agency
local function teleportToPortalAgency()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(672, 4, -296)
end

AddButton(Main, {
    Name = "تـنـقـل / 1",
    Description = "",
    Callback = teleportToCenter
})

-- Function to teleport to Criminal
local function teleportToCriminal()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-119, -28, 235)
end

AddButton(Main, {
    Name = "تـنـقـل / 2",
    Description = "Teleporta para as coordenadas do Criminal",
    Callback = teleportToCriminal
})

-- Function to teleport to House Abandoned
local function teleportToHouseAbandoned()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(986, 4, 63)
end

AddButton(Main, {
    Name = "تـنـقـل / 3",
    Description = "Teleporta para as coordenadas da Casa Abandonada",
    Callback = teleportToHouseAbandoned
})

-- Function to teleport to Portal Agency
local function teleportToPortalAgency()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(672, 4, -296)
end

AddButton(Main, {
    Name = "تـنـقـل / 4",
    Description = "Teleporta para as coordenadas do Portal da Agأھncia",
    Callback = teleportToPortalAgency
})

-- Function to teleport to Secret Location
local function teleportToSecretLocation()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(505, -75, 143)
end

AddButton(Main, {
    Name = "تـنـقـل / 5",
    Description = "Teleporta para as coordenadas do Local Secreto",
    Callback = teleportToSecretLocation
})

-- Function to teleport to School
local function teleportToSchool()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-312, 4, 211)
end

AddButton(Main, {
    Name = "تـنـقـل / 6",
    Description = "Teleporta para as coordenadas da Escola",
    Callback = teleportToSchool
})

-- Function to teleport to Brooks Diner
local function teleportToBrooksDiner()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(161, 8, 52)
end

AddButton(Main, {
    Name = "تـنـقـل / 7",
    Description = "Teleporta para as coordenadas do Brooks Diner",
    Callback = teleportToBrooksDiner
})

local function teleportToBrooksDiner()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-26, 4, -23)
end

AddButton(Main, {
    Name = "تـنـقـل / 8",
    Description = "Teleporta para as coordenadas do Brooks Diner",
    Callback = teleportToBrooksDiner
})


-- Function to teleport to Hospital
local function teleportToHospital()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-309, 4, 71)
end

AddButton(Main, {
    Name = "تـنـقـل / 9",
    Description = "Teleporta para as coordenadas do Hospital",
    Callback = teleportToHospital
})
-- Function to teleport to Secret Room 2
local function teleportToSecretRoom2()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-343, 4, -613)
end

AddButton(Main, {
    Name = "تـنـقـل / 10",
    Description = "Teleporta para as coordenadas da Sala Secreta 2",
    Callback = teleportToSecretRoom2
})

-- Function to teleport to Island 1
local function teleportToIsland1()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1925, 23, 127)
end

AddButton(Main, {
    Name = "تـنـقـل / 11",
    Description = "Teleporta para as coordenadas da Ilha 1",
    Callback = teleportToIsland1
})

-- Function to teleport to Airport
local function teleportToAirport()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(310, 5, 31)
end

AddButton(Main, {
    Name = "تـنـقـل / 12",
    Description = "Teleporta para as coordenadas do Aeroporto",
    Callback = teleportToAirport
})

-- Function to teleport to Arch
local function teleportToArch()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-589, 141, -59)
end

AddButton(Main, {
    Name = "تـنـقـل / 12",
    Description = "Teleporta para as coordenadas do Arco",
    Callback = teleportToArch
})

-- Function to teleport to Agency
local function teleportToAgency()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(179, 4, -464)
end

AddButton(Main, {
    Name = "تـنـقـل / 13",
    Description = "Teleporta para as coordenadas da Agأھncia",
    Callback = teleportToAgency
})

AddButton(Main, {
    Name = "مكان سري",
    Description = "Teleporta para as coordenadas do Portal da Agência",
    Callback = teleportToPortalAgency
})

-- Function to teleport to Secret Location
local function teleportToSecretLocation()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(505, -75, 143)
end

AddButton(Main, {
    Name = "تحت الارض",
    Description = "Teleporta para as coordenadas do Local Secreto",
    Callback = teleportToSecretLocation
})

-- Function to teleport to School
local function teleportToSchool()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-312, 4, 211)
end

AddButton(Main, {
    Name = "مدرسة",
    Description = "Teleporta para as coordenadas da Escola",
    Callback = teleportToSchool
})

-- Function to teleport to Brooks Diner
local function teleportToBrooksDiner()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(161, 8, 52)
end

AddButton(Main, {
    Name = "قهوة",
    Description = "Teleporta para as coordenadas do Brooks Diner",
    Callback = teleportToBrooksDiner
})

local function teleportToBrooksDiner()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-26, 4, -23)
end

AddButton(Main, {
    Name = "البداية",
    Description = "Teleporta para as coordenadas do Brooks Diner",
    Callback = teleportToBrooksDiner
})


-- Function to teleport to Hospital
local function teleportToHospital()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-309, 4, 71)
end

AddButton(Main, {
    Name = "مستشفى",
    Description = "Teleporta para as coordenadas do Hospital",
    Callback = teleportToHospital
})

-- Function to teleport to Arch
local function teleportToArch()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-589, 141, -59)
end

AddButton(Main, {
    Name = "فوق الجسر",
    Description = "Teleporta para as coordenadas do Arco",
    Callback = teleportToArch
})

-- Function to teleport to Agency
local function teleportToAgency()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(179, 4, -464)
end

AddButton(Main, {
    Name = "مكان الكهرباء",
    Description = "Teleporta para as coordenadas da Agência",
    Callback = teleportToAgency
})

-- Function to teleport to Secret Room in Workshop
local function teleportToSecretRoomInWorkshop()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(0, 4, -495)
end

AddButton(Main, {
    Name = "جو الأرض",
    Description = "Teleporta para as coordenadas da Sala Secreta na Oficina",
    Callback = teleportToSecretRoomInWorkshop
})

-- Function to teleport to Secret Room 2
local function teleportToSecretRoom2()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-343, 4, -613)
end

AddButton(Main, {
    Name = "جو الأرض 2",
    Description = "Teleporta para as coordenadas da Sala Secreta 2",
    Callback = teleportToSecretRoom2
})

-- Function to teleport to Island 1
local function teleportToIsland1()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1925, 23, 127)
end

AddButton(Main, {
    Name = "جزيرة 1",
    Description = "Teleporta para as coordenadas da Ilha 1",
    Callback = teleportToIsland1
})

-- Function to teleport to Airport
local function teleportToAirport()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(310, 5, 31)
end

AddButton(Main, {
    Name = "مطار",
    Description = "Teleporta para as coordenadas do Aeroporto",
    Callback = teleportToAirport
})

-- Function to teleport to Hotel Center
local function teleportToHotelCenter()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(182, 4, 150)
end

AddButton(Main, {
    Name = "البيوت",
    Description = "Teleporta para as coordenadas do Centro dos Hotéis",
    Callback = teleportToHotelCenter
})

-- Function to teleport to Lower Houses
local function teleportToLowerHouses()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(63, 35, 410)
end

AddButton(Main, {
    Name = " نص الشارع",
    Description = "Teleporta para as coordenadas das Casas Inferiores",
    Callback = teleportToLowerHouses
})

-- Function to teleport to Mountain 1
local function teleportToMountain1()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-670, 251, 765)
end

AddButton(Main, {
    Name = "فوق الجبل",
    Description = "Teleporta para as coordenadas da Montanha 1",
    Callback = teleportToMountain1
})

-- Function to teleport to On Top of School
local function teleportToOnTopOfSchool()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-370, 50, 173)
end

AddButton(Main, {
    Name = "فوق المدرسة",
    Description = "Teleporta para as coordenadas Em Cima da Escola",
    Callback = teleportToOnTopOfSchool
})

local Main = MakeTab({Name = "الرؤوس والارجل"})
AddSection(Main, {"الأرجل"})

AddButton(Main, {
    Name = " رجل مقطوعه للبنت ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 96491916349570;
                [2] = 76683091425509;
                [3] = 75159926897589;
                [4] = 139607718;
                [5] = 1;
                [6] = 1;
            };
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " رجل مقطوعه للولد ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 1;
                [2] = 1;
                [3] = 1;
                [4] = 139607718;
                [5] = 1;
                [6] = 1;
            };
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " رجل حديديه طويله ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 1;
                [2] = 1;
                [3] = 1;
                [4] = 17500249989;
                [5] = 1;
                [6] = 1;
            };
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " رجل العضام السوداء الطويله ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 1;
                [2] = 1;
                [3] = 1;
                [4] = 14547162578;
                [5] = 1;
                [6] = 1;
            };
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " رجل العضام البيضاء الطويله ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 1;
                [2] = 1;
                [3] = 1;
                [4] = 14580308646;
                [5] = 1;
                [6] = 1;
            };
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " رجل الرول ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 1;
                [2] = 1;
                [3] = 1;
                [4] = 3230472745;
                [5] = 3230470862;
                [6] = 1;
            };
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddSection(Main, {"الرؤوس"})

AddButton(Main, {
    Name = " راس روبوت او فضائي ",
    Callback = function()
        local args = {
            [1] = 3210773801;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("Wear", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " راس مخفي ",
    Callback = function()
        local args = {
            [1] = 134082579;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("Wear", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " راس عيون زرقاء المخفي ",
    Callback = function()
        local args = {
            [1] = 16580493236;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("Wear", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " راس كوبي او الرول ",
    Callback = function()
        local args = {
            [1] = 746767604;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("Wear", 9e9):InvokeServer(unpack(args))
    end
})


local Main = MakeTab({Name = " الاجسام"})
AddSection(Main, {" اجسام اولاد وبنات"})

AddButton(Main, {
    Name = "  جسم بنت خصر صغير  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 96491916349570;
                [2] = 76683091425509;
                [3] = 75159926897589;
                [4] = 1;
                [5] = 1;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم بنت خصر ضعيف  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 74302534603111;
                [2] = 76683091425509;
                [3] = 75159926897589;
                [4] = 1;
                [5] = 1;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم بنت رقم 1  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 96491916349570;
                [2] = 14854350570;
                [3] = 14854350451;
                [4] = 1;
                [5] = 1;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم بنت رقم 2  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 16214246112;
                [2] = 16214249513;
                [3] = 16214251181;
                [4] = 1;
                [5] = 1;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم بنت رقم 3  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 15539008532;
                [2] = 15539008875;
                [3] = 15539008680;
                [4] = 15539008795;
                [5] = 15539011945;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم بنت رقم 4  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 14861800638;
                [2] = 14861800626;
                [3] = 14861801452;
                [4] = 14861800627;
                [5] = 14861801454;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم ولد يجنن  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 17754346388;
                [2] = 1;
                [3] = 1;
                [4] = 1;
                [5] = 1;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم ولد ضعيف  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 92757812011061;
                [2] = 99519402284266;
                [3] = 115905570886697;
                [4] = 1;
                [5] = 1;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم ولد رول  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 27112025;
                [2] = 27112039;
                [3] = 27112052;
                [4] = 3230472745;
                [5] = 3230470862;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم ولد كوبي  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 86499666;
                [2] = 27112039;
                [3] = 27112052;
                [4] = 27112068;
                [5] = 27112056;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم ولد معضل  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 18178775358;
                [2] = 18178775182;
                [3] = 18178775725;
                [4] = 18178777453;
                [5] = 18178775695;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddSection(Main, {" اجسام القزم "})

AddButton(Main, {
    Name = "  جسم القزم  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 14579958702;
                [2] = 14579959062;
                [3] = 14579959191;
                [4] = 14579959249;
                [5] = 14579963667;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم القزم المتوسط  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 77813057823038;
                [2] = 135110043370135;
                [3] = 116607813654019;
                [4] = 138966229804486;
                [5] = 128961183894053;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم القزم القصير  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 120973199097564;
                [2] = 118345433416023;
                [3] = 112849465115864;
                [4] = 78321005147549;
                [5] = 106586789635639;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم القزم المتوسط تقريباً  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 126267841602936;
                [2] = 77530451194918;
                [3] = 123471958406889;
                [4] = 117042768644173;
                [5] = 131948590344338;
                [6] = 1;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم الهامستر  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 14898536974;
                [2] = 14898536957;
                [3] = 14898537277;
                [4] = 14898537300;
                [5] = 14898537292;
                [6] = 14898536975;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddSection(Main, {" اجسام غريبه عجييه "})

AddButton(Main, {
    Name = "  جسم روبوت  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 14776593226;
                [2] = 14776227941;
                [3] = 14776227816;
                [4] = 102149844389538;
                [5] = 102624006545764;
                [6] = 74920391713702;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم هالك  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 105938035513300;
                [2] = 120682289281525;
                [3] = 78459091342559;
                [4] = 119167161940457;
                [5] = 78171925423915;
                [6] = 92193892051712;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = "  جسم كرسي  ",
    Callback = function()
        local args = {
            [1] = {
                [1] = 16872133248;
                [2] = 16872133982;
                [3] = 16872133723;
                [4] = 16872133730;
                [5] = 16872133733;
                [6] = 134082579;
            };
        }

        game:GetService("ReplicatedStorage"):WaitForChild("Remotes", 9e9):WaitForChild("ChangeCharacterBody", 9e9):InvokeServer(unpack(args))
    end
})

local Main = MakeTab({Name = " الملابس"})
AddSection(Main, {"اولاً يا عزيز ازل الملابس لضمان جوده افضل"})

AddButton(Main, {
  Name = "ازاله ملابس",
  Callback = function()
    local args = {
    [1] = "wear",
    [2] = 2248242028
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
wait(0.1)

   local args = {
    [1] = "wear",
    [2] = 2547392639
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
wait(0.1)
  end
})

AddSection(Main, {"نسخ سكنات كاملة"})

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")
local StarterGui = game:GetService("StarterGui")

local RemoteWear = ReplicatedStorage:WaitForChild("Remotes"):WaitForChild("Wear")
local RemoteBody = ReplicatedStorage:WaitForChild("Remotes"):WaitForChild("ChangeCharacterBody")

local function Notify(title, text)
    StarterGui:SetCore("SendNotification", {
        Title = title,
        Text = text,
        Duration = 3
    })
end

local function Wear(id)
    if id and id ~= 0 then
        RemoteWear:InvokeServer(id)
    end
end

local function RemoveOldClothes()
    local character = Players.LocalPlayer.Character or Players.LocalPlayer.CharacterAdded:Wait()
    for _, item in pairs(character:GetChildren()) do
        if item:IsA("Shirt") or item:IsA("Pants") then
            item:Destroy()
        end
    end
end

local function ApplySkinTone(player)
    local char = player.Character or player.CharacterAdded:Wait()
    local bodyColors = char:FindFirstChildOfClass("BodyColors")
    if bodyColors then
        Wear(bodyColors.HeadColor.Name)
    end
end

local function CopyClothing(player)
    local h = (player.Character or player.CharacterAdded:Wait()):FindFirstChildOfClass("Humanoid")
    if h then
        local d = h:GetAppliedDescription()
        for _, id in ipairs({d.Shirt, d.Pants, d.GraphicTShirt}) do
            Wear(id)
            task.wait(0.2)
        end
    end
end

local function CopyAccessories(player)
    local h = (player.Character or player.CharacterAdded:Wait()):FindFirstChildOfClass("Humanoid")
    if h then
        local d = h:GetAppliedDescription()
        local all = {
            d.HatAccessory, d.HairAccessory, d.FaceAccessory,
            d.NeckAccessory, d.ShouldersAccessory, d.FrontAccessory,
            d.BackAccessory, d.WaistAccessory
        }
        for _, accList in ipairs(all) do
            for id in string.gmatch(accList, "%d+") do
                Wear(tonumber(id))
                task.wait(0.2)
            end
        end
    end
end

local function CopyBodyParts(player)
    local h = (player.Character or player.CharacterAdded:Wait()):FindFirstChildOfClass("Humanoid")
    if h then
        local d = h:GetAppliedDescription()
        local bodyIds = {
            d.Torso, d.RightArm, d.LeftArm,
            d.RightLeg, d.LeftLeg, d.Head
        }
        RemoteBody:InvokeServer(bodyIds)
    end
end

local selectedPlayer = nil

local function GetPlayerList()
    local list = {}
    for _, p in ipairs(Players:GetPlayers()) do
        if p ~= Players.LocalPlayer then
            table.insert(list, p.Name)
        end
    end
    return list
end

AddDropdown(Main, {
    Name = "اختار اللاعب",
    Default = "",
    Options = GetPlayerList(),
    Callback = function(value)
        selectedPlayer = value
    end
})

AddButton(Main, {
    Name = "نسخ السكن",
    Callback = function()
        if not selectedPlayer then
            Notify("خطأ", "يجب اختيار لاعب أولاً")
            return
        end

        local player = Players:FindFirstChild(selectedPlayer)
        if not player then return end

        Notify("جاري النسخ", "جاري نسخ سكن " .. player.Name)

        task.spawn(function()
            RemoveOldClothes()
            task.wait(0.5)
            CopyBodyParts(player)
            task.wait(0.3)
            ApplySkinTone(player)
            task.wait(0.3)
            CopyClothing(player)
            task.wait(0.3)
            CopyAccessories(player)
            Notify("تم النسخ", "تم نسخ سكن " .. player.Name .. " بنجاح!")
        end)
    end
})


AddSection(Main, {" أحذية الشيطان "})

AddButton(Main, {
    Name = " حذاء الشيطان الأبيض ",
    Callback = function()
        local args = {
            [1] = 14388009243;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " حذاء الشيطان الأسود والأحمر ",
    Callback = function()
        local args = {
            [1] = 14388001192;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " حذاء الشيطان الأسود ",
    Callback = function()
        local args = {
            [1] = 14388004031;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddSection(Main, {" شوك "})

AddButton(Main, {
    Name = " شوك أسود بالذراع والساق ",
    Callback = function()
        local args = {
            [1] = 17406577951;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " شوك أبيض بالذراع والساق ",
    Callback = function()
        local args = {
            [1] = 17406634097;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " شوك أسود حول كامل الجسم ",
    Callback = function()
        local args = {
            [1] = 13463285148;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddSection(Main, {" باقات ورد "})

AddButton(Main, {
    Name = " باقة ورد سوداء ",
    Callback = function()
        local args = {
            [1] = 12465465333;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " باقة ورد حمراء ",
    Callback = function()
        local args = {
            [1] = 86738633187728;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " باقة ورد وردية ",
    Callback = function()
        local args = {
            [1] = 12465478536;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " باقة ورد بيضاء ",
    Callback = function()
        local args = {
            [1] = 72175664063418;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddSection(Main, {" ضمادات الذراع "})

AddButton(Main, {
    Name = " ضمادات الذراع لون أسود ",
    Callback = function()
        local args = {
            [1] = 11456892689;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " ضمادات الذراع لون أبيض ",
    Callback = function()
        local args = {
            [1] = 11458078735;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddSection(Main, {" قفازات "})

AddButton(Main, {
    Name = " قفازات اليد طويلة لون أسود ",
    Callback = function()
        local args = {
            [1] = 14663501859;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات قصيرة لون أسود ",
    Callback = function()
        local args = {
            [1] = 14915193711;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات اليد طويلة لون أحمر ",
    Callback = function()
        local args = {
            [1] = 15209194774;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات اليد طويلة لون أبيض ",
    Callback = function()
        local args = {
            [1] = 10789933479;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات قصيرة لون أبيض ",
    Callback = function()
        local args = {
            [1] = 15066901505;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات اليد طويلة لون أزرق ",
    Callback = function()
        local args = {
            [1] = 10789945803;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات قصيرة لون أزرق ",
    Callback = function()
        local args = {
            [1] = 10714157708;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات اليد طويلة لون وردي ",
    Callback = function()
        local args = {
            [1] = 10789939838;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات قصيرة لون وردي ",
    Callback = function()
        local args = {
            [1] = 17775444165;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات اليد طويلة لون أخضر ",
    Callback = function()
        local args = {
            [1] = 13233318125;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات قصيرة لون أخضر ",
    Callback = function()
        local args = {
            [1] = 10713817180;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفاز غريب ",
    Callback = function()
        local args = {
            [1] = 12175951307;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات حمراء مخططة لون أبيض ",
    Callback = function()
        local args = {
            [1] = 14687547890;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات تتناسب على البنت أو الولد ",
    Callback = function()
        local args = {
            [1] = 106701020164834;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات وردية للبنات ",
    Callback = function()
        local args = {
            [1] = 16030963309;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات سوداء جميلة ",
    Callback = function()
        local args = {
            [1] = 12368927792;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات بيضاء جميلة ",
    Callback = function()
        local args = {
            [1] = 12368919975;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات خضراء جميلة ",
    Callback = function()
        local args = {
            [1] = 12368854118;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات مخططة أسود وأحمر ",
    Callback = function()
        local args = {
            [1] = 14758885890;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " قفازات مخططة أبيض وأسود ",
    Callback = function()
        local args = {
            [1] = 14758885890;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddSection(Main, {" جاكيتات "})

AddButton(Main, {
    Name = " جاكيت أسود مفتوح ",
    Callback = function()
        local args = {
            [1] = 9048321833;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " جاكيت أسود فيه هيكل عظمي مفتوح ",
    Callback = function()
        local args = {
            [1] = 15154273975;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " جاكيت أسود وأبيض مفتوح ",
    Callback = function()
        local args = {
            [1] = 9122099141;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " جاكيت أبيض مفتوح ",
    Callback = function()
        local args = {
            [1] = 11247067714;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})

AddButton(Main, {
    Name = " جاكيت أسود مفتوح حلو ",
    Callback = function()
        local args = {
            [1] = 9132711224;
        }
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes",9e9):WaitForChild("Wear",9e9):InvokeServer(unpack(args))
    end
})
