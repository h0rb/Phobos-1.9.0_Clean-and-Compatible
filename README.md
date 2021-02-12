# Phobos-1.9.0_Clean-and-Compatible
this one looks like works with pyro 1.4.1. Still, there might be compatibility issues because of mixin configs or something idk have fun

Credit goes to Gopro's phobos buildable src. 
https://github.com/Gopro336/CLEAN_Phobos_1.9.0-BUILDABLE-SRC

IMPORTANT NOTE:
you need to modify the required: true to false in mixins.pyroclient.json in your pyro jar. 


CHANGES I'VE DONE:

changed mixins.phobos.json required: true to false

changed mixinminecraft:
Original one:

   ` @Redirect(method={"rightClickMouse"}, at=@At(value="INVOKE", target="Lnet/minecraft/client/multiplayer/PlayerControllerMP;getIsHittingBlock()Z", ordinal=0),require =1)
    private boolean isHittingBlockHook(PlayerControllerMP playerControllerMP) {
        return !MultiTask.getInstance().isOn() && playerControllerMP.getIsHittingBlock();
    }`
    
My version:

   ` @Redirect(method={"rightClickMouse"}, at=@At(value="INVOKE", target="Lnet/minecraft/client/multiplayer/PlayerControllerMP;getIsHittingBlock()Z", ordinal=0))
    private boolean isHittingBlockHook(PlayerControllerMP playerControllerMP) {
        return !MultiTask.getInstance().isOn() && playerControllerMP.getIsHittingBlock();
    }`
