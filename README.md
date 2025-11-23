local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "idk Hub",
   Icon = nil, -- ou assetId válido em string
   LoadingTitle = "idk Hub",
   LoadingSubtitle = "by idk",
   Theme = "Dark",
   ToggleUIKeybind = "K",

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false,

   ConfigurationSaving = {
      Enabled = true,
      FolderName = idk hub,
      FileName = "idk Hub"
   },

   Discord = {
      Enabled = false,
      Invite = "noinvitelink",
      RememberJoins = false
   },

   KeySystem = false,
   KeySettings = {
      Title = "idk Keys",
      Subtitle = "Key System",
      Note = "Para conseguir a key, entre no discord da idk",
      FileName = "Key",
      SaveKey = true,
      GrabKeyFromSite = false,
      Key = {"idk""}
   }
})

local idkHub = Window:CreateTab("idk Hub", 4483362458)
local Farm = Window:CreateTab("Farm", 4483362458)

local SectionMain = idkHub:CreateSection("Funções Principais")

local function Equipar melhores personagens de anime()
   local args = {
      "equipBestNPCs"
   }
   game:GetService("ReplicatedStorage"):WaitForChild("Packages"):WaitForChild("Networker"):WaitForChild("leifstout_networker@0.3.0"):WaitForChild("networker"):WaitForChild("_remotes"):WaitForChild("EquipBest"):WaitForChild("RemoteEvent"):FireServer(unpack(args))
   
   end
end

local ButtonKill = Farm:CreateButton({
   Name = "Matar Jogador",
   Callback = MatarJogador
})

local ToggleFlash = idkHub:CreateToggle({
   Name = "Flash",
   CurrentValue = false,
   Callback = function(Value)
      local player = game.Players.LocalPlayer
      if player and player.Character and player.Character:FindFirstChild("Humanoid") then
         if Value then
            player.Character.Humanoid.WalkSpeed = 50
         else
            player.Character.Humanoid.WalkSpeed = 16
         end
      end
   end
})

local SliderJump = Farm:CreateSlider({
   Name = "Pulo (JumpPower)",
   Range = {0, 100},
   Increment = 1,
   Suffix = "", -- sem '%'
   CurrentValue = 50,
   Callback = function(Value)
      local player = game.Players.LocalPlayer
      if player and player.Character and player.Character:FindFirstChild("Humanoid") then
         player.Character.Humanoid.JumpPower = Value
      end
   end
})

local SectionNPC = Farm:CreateSection("NPCs")

local InputNPC = Farm:CreateInput({
   Name = "Nome do NPC",
   PlaceholderText = "Digite um NPC...",
   RemoveTextAfterFocusLost = false,
   Callback = function(Text)
      -- aqui você pode adicionar ação para o texto digitado
   end
})

local DropdownNPC = Farm:CreateDropdown({
   Name = "Selecionar NPC",
   Options = {"Npc 1", "Npc 2", "Npc 3"},
   CurrentOption = "Npc 1",
   Callback = function(Option)
      -- ação para opção selecionada
   end
})

local SectionExtra = Farm:CreateSection("Extras")

local KeybindExample = Farm:CreateKeybind({
   Name = "Atalho de Teclado",
   CurrentKeybind = "F",
   HoldToInteract = false,
   Callback = function(Key)
      -- ação ao pressionar a tecla
   end
})

local ParagraphCreator = Farm:CreateParagraph({
   Title = "Criador",
   Content = "idk Hub by idk"
})

Rayfield:LoadConfiguration()
