local bundleId = 39

local AssetService = game:GetService(‘AssetService’)
local MarketplaceService = game:GetService(‘MarketplaceService’)

local BundleItems = AssetService:GetBundleDetailsAsync(bundleId).Items

local FirstBundleInfo = MarketplaceService:GetProductInfo(BundleItems[1].Id)

local OldBundleId = string.match(FirstBundleInfo.Description, “%d+”)

MarketplaceService:PromptPurchase(game.Players.LocalPlayer, OldBundleId)
