AnimatedDecouplers
==================

Extensions of KSP's decouplers that play animations


Configure the same way as you would standard decoupler modules but it now accepts animationName, which is the name of an animation on the model.

If the model has no animation or no animation name is configured then these function exactly as stock decouplers.

For example:

	MODULE
	{
	    name = ModuleAnimatedDecoupler
	    ejectionForce = 200
	    explosiveNodeID = top
	    staged = false
	    animationName = SDHI_Umbilical
		waitForAnimation = false // (If true, then delay decoupling until animation has finished playing)
		layer = 1 // Animation's layer will be set to this. Helps prevent multiple animations on one part interfering with each other
	}
	
Additionally, if ModuleCargoBay is configured on the part and DeployModuleIndex has the module index for the decoupler provided (0 = first) then the part will shield enclosed parts in KSP 1.0 and beyond. (against aerothermodynamic forces)


Changelog
Version 1.3.5
* Recompiled for KSP 1.3.1

Version 1.3.4
* Recompiled for KSP 1.3.0

Version 1.3.3
* Recompiled for KSP 1.2.1

Version 1.3.2
* Recompiled for KSP 1.1.3

Version 1.3.1
* Recompiled for KSP 1.1

Version 1.3.0
* Additional checks for null references
* Reworking of code; extraneous code removed. (deploy checks for occlusion purposes that were later determined to be unnecessary)

Version 1.2.0

* Added waitForAnimation. (if true, decoupling will be delayed until animation has completed)
* Added layer field, requiring an integer. If set, part's animation layer will be set to this. (unique layers per animation help prevent animations from canceling one another)
* Added check for null animator. (if no animation was set and found then don't delay decoupling)
* General reworking of code.

Version 1.2.1

* Added extra checks for null references. (fixes certain issues in staging. i.e. only one of multiple symmetrical decouplers firing or one part of any staging group firing)