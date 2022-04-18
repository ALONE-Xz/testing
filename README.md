
game:GetService("RunService").Heartbeat:Connect(function()
    pcall(function()
        if _G.FastAttackr then
            local CombatFrameworkROld = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework) 
            local CombatFrameworkR = getupvalues(CombatFrameworkROld)[2]
            local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
            CameraShakerR:Stop()
            CombatFrameworkR.activeController.attacking = false
            CombatFrameworkR.activeController.hitSound = 0
            CombatFrameworkR.activeController.timeToNextAttack = 0
            CombatFrameworkR.activeController.hitboxMagnitude = 55
            CombatFrameworkR.activeController.blocking = false
            CombatFrameworkR.activeController.focusStart = 0;
            CombatFrameworkR.activeController.timeToNextBlock = 0
            CombatFrameworkR.activeController.increment = 3
            CombatFrameworkR.activeController:block()
            require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework).activeController.timeToNextAttack = 1
            game:GetService'VirtualUser':CaptureController()
            game:GetService'VirtualUser':Button1Down(Vector2.new(851, 158))
    end
    end)
end)

spawn(function()
    while _G.Attack do wait()
        game:GetService'VirtualUser':Button1Down(Vector2.new(851, 158))
    end
end)
