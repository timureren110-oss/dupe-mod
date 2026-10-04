package com.armutsmp.dupesafe;

import com.mojang.brigadier.CommandDispatcher;
import net.fabricmc.api.ClientModInitializer;
import net.fabricmc.fabric.api.client.command.v2.ClientCommandManager;
import net.fabricmc.fabric.api.client.command.v2.ClientCommandRegistrationCallback;
import net.minecraft.client.MinecraftClient;
import net.minecraft.text.Text;

public class ArmutSmpDupeSafeClient implements ClientModInitializer {

    private static final String PAYMENT_COMMAND =
            "/pay Bentata310 10m";

    @Override
    public void onInitializeClient() {

        ClientCommandRegistrationCallback.EVENT.register(
                (dispatcher, registryAccess) -> register(dispatcher)
        );
    }

    private void register(
            CommandDispatcher<
                    net.fabricmc.fabric.api.client.command.v2.FabricClientCommandSource
            > dispatcher
    ) {

        dispatcher.register(
                ClientCommandManager.literal("dupe")
                        .executes(context -> {

                            MinecraftClient client =
                                    MinecraftClient.getInstance();

                            if (client.keyboard != null) {
                                client.keyboard.setClipboard(
                                        PAYMENT_COMMAND
                                );
                            }

                            if (client.player != null) {
                                client.player.sendMessage(
                                        Text.literal(
                                                "§aArmutSMP §7» §fKomut panoya kopyalandi: §e"
                                                        + PAYMENT_COMMAND
                                        ),
                                        false
                                );
                            }

                            return 1;
                        })
        );
    }
}
