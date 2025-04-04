# voltage-regulators
This Repository host Linux device driver for Infineon Digital Multiphase Controllers and Voltage Regulators.

This release includes:
1. README (this file).
2. Kernel patch "0001-PMBUS-DRIVER-Support-for-Infineon-Devices" can be applied to Kernel source(6.6.58).
3. Kernel patch "0002-IFX-PMBUS-DRIVER-PEC-RETRY" for handling retry in case of PEC and NACK Error.
4. GNU GPL File 
5. tda38740 driver testing log as tda38740_driver_log File

This tda38740 driver includes Infineon device driver for:
1. Integrated-POL-Voltage-Regulators: TDA38725, TDA38725A, TDA38740, TDA38740A
2. Digital-Multiphase-Controllers: XDPE1A2G5B, XDPE19284C, XDPE192C4B

NOTE:
1. This Driver is scalable for other Infineon devices as per requirements.
2. We need to provide vout_multiplier values from Device Tree. 
   Examples:

	tda38740@76 {
		compatible = "infineon,xdpe192c4b";
		reg = <0x76>;
	};

	tda38740@40 {
		compatible = "infineon,tda38740a";
		reg = <0x40>;
		vout_multiplier = <70 75>;
	};

	tda38740@4F {
		compatible = "infineon,tda38725a";
		reg = <0x4F>;
		vout_multiplier = <80 60>;
	};

3. This driver can be optimized in case required like clubbing similar functionality devices.
   
