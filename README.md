- 👋 Hi, I’m @STOCKHAMMER-4663-RAHSTORF-21
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
STOCKHAMMER-4663-RAHSTORF-21/STOCKHAMMER-4663-RAHSTORF-21 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

DCSWORLD OpenBeta_: 

-- Leopard-2A6M

GT = {};
GT_t.ws = 0;
set_recursive_metatable(GT, GT_t.generic_tank);
set_recursive_metatable(GT.chassis, GT_t.CH_t.LEOPARD2A5);

GT.visual.shape = "leopard-2";
GT.visual.shape_dstr = "Leopard-2_p_1";
GT.toggle_alarm_state_interval = 4.0;

GT.IR_emission_coeff = 0.12

-- Turbine
GT.turbine = false;
-- Turbine

-- Crew

GT.crew_locale = "ENG";
GT.crew_members = {"commander", "gunner"};

-- Crew

--chassis
GT.swing_on_run = false;


GT.sensor = {};
set_recursive_metatable(GT.sensor, GT_t.SN_visual);
GT.sensor.height = 2.738;

--Burning after hit
GT.visual.fire_size = 0.6; --relative burning size
GT.visual.fire_pos[1] = -2.3; -- center of burn at long axis shift(meters)
GT.visual.fire_pos[2] = 0.7; -- center of burn shift at vertical shift(meters)
GT.visual.fire_pos[3] = 0; -- center of burn at transverse axis shift(meters)
GT.visual.fire_time = 1200; --burning time (seconds)
GT.visual.dust_pos = {3.6, 0.2, -GT.chassis.Z_gear_1}
GT.visual.dirt_pos = {-3.4, 0.8, -GT.chassis.Z_gear_2}

GT.DM = {
	{ area_name = "GLACIS", 					armour = {width=0.070}},
	{ area_name = "Telo_VLD", 					armour = {width=0.450}},
	{ area_name = "Telo_NLD", 					armour = {width=0.350}},
	{ area_name = "Telo_NIZ", 					armour = {width=0.070}},
	{ area_name = "Telo_BORT_Lev", 				armour = {width=0.080}},
	{ area_name = "Telo_BORT_Prav", 			armour = {width=0.080}},
	{ area_name = "KDZ_Lev", 					armour = {width=0.130}},
	{ area_name = "KDZ_Prav", 					armour = {width=0.130}},
	{ area_name = "Falshbort_Lev", 				armour = {width=0.080}},
	{ area_name = "Falshbort_Prav", 			armour = {width=0.080}},
	{ area_name = "Telo_ZAD", 					armour = {width=0.030}},
	{ area_name = "Telo_VERH", 					armour = {width=0.030}},
	{ area_name = "Telo_MTO", 					armour = {width=0.030}},
	
	{ area_name = "Bashnya_LOB",				armour = {width=0.500}},
	{ area_name = "Bashnya_Dop_BORT_Lev",		armour = {width=0.500}},
	{ area_name = "Bashnya_Dop_BORT_Prav",		armour = {width=0.500}},
	{ area_name = "Bashnya_BORT_Lev",			armour = {width=0.300}},
	{ area_name = "Bashnya_BORT_Prav",			armour = {width=0.300}},
	{ area_name = "Bashnya_ZAD",				armour = {width=0.025}},
	{ area_name = "Bashnya_NIZ",				armour = {width=0.040}},
	{ area_name = "Bashnya_VERH",				armour = {width=0.070}},
	{ area_name = "Bashnya_VERH_2",				armour = {width=0.040}},
	{ area_name = "Pricel_1",					armour = {width=1.0}}, -- inert
	{ area_name = "Pricel_1_top",				armour = {width=0.040}},
	{ area_name = "Pricel_2",					armour = {width=1.0}}, -- inert
	{ area_name = "Pricel_2_top",				armour = {width=0.040}},
	{ area_name = "Luk_Zar",					armour = {width=0.040}},
	{ area_name = "Luk_Kom",					armour = {width=0.040}},

	{ area_name = "Guslya_Lev", 				armour = {width=0.200}},
	{ area_name = "Guslya_Lev_Front", 			armour = {width=1.500}},
	{ area_name = "Guslya_Prav", 				armour = {width=0.200}},
	{ area_name = "Guslya_Prav_Front", 			armour = {width=1.500}},

	{ area_name = "Orudie_Maska",				armour = {width=0.500}},
	{ area_name = "Orudie", 					armour = {width=0.400}},
	
}


GT.driverViewConnectorName = {"DRIVER_POINT", offset = {0.05, 0.0, 0.0}}
GT.driverCockpit = "DriverCockpit/DriverCockpitWithIR"

-- weapon systems
GT.WS = {};
GT.WS.maxTargetDetectionRange = 6000;
GT.WS.smoke = {"SMOKE_01", "SMOKE_02", "SMOKE_03", "SMOKE_04", "SMOKE_05", "SMOKE_06", "SMOKE_07", "SMOKE_08",
                "SMOKE_09", "SMOKE_10", "SMOKE_11", "SMOKE_12", "SMOKE_13", "SMOKE_14", "SMOKE_15", "SMOKE_16"};

local ws = GT_t.inc_ws();
GT.WS[ws] = {};
GT.WS[ws].center = 'CENTER_TOWER';
GT.WS[ws].pointer = "POINT_SIGHT_01"; -- connector name
GT.WS[ws].cockpit = { "EMES-15/EMES-15", {0.0, 0.0, 0.0 }, };
GT.WS[ws].angles = {
                    {math.rad(140), math.rad(-140), math.rad(-9), math.rad(19)},
                    {math.rad(-140), math.rad(140), math.rad(0), math.rad(19)},
                    };
GT.WS[ws].drawArgument1 = 0;
GT.WS[ws].drawArgument2 = 1;
GT.WS[ws].omegaY = math.rad(48);
GT.WS[ws].omegaZ = math.rad(20);
GT.WS[ws].pidY = MODERN_TANK_TOWER_PIDY
GT.WS[ws].pidZ = MODERN_TANK_TOWER_PIDZ
GT.WS[ws].stabilizer = true;
GT.WS[ws].laser = true;

--GT.WS[1].LN[1]
__LN = add_launcher(GT.WS[ws], GT_t.LN_t.tank_gun_120mm);
__LN.beamWidth = math.rad(1);
__LN.BR[1] = {connector_name = 'POINT_GUN_01',
			recoilArgument = 23,
			recoilTime = 0.3};
__LN.PL[1].shell_name = {"M256_120_AP_L55"};
__LN.PL[1].ammo_capacity = 9
__LN.PL[1].reload_time = 15 * 9
__LN.PL[1].shot_delay = 6
__LN.PL[2].shell_name = {"M256_120_AP_L55"};
__LN.PL[2].ammo_capacity = 16
__LN.PL[2].reload_time = 15 * 16
__LN.PL[2].shot_delay = 10
__LN.PL[1].virtualStwID = 1;
__LN.PL[2].virtualStwID = 2;
__LN.sightMasterMode = 1;
__LN.sightIndicationMode = 1;
--GT.WS[1].LN[2]
__LN = add_launcher(GT.WS[ws], __LN); -- HE gun
__LN.type = 6;
__LN.distanceMin = 20;
__LN.distanceMax = 8000;
__LN.PL[1].shell_name = {"M256_120_HE_L55"};
__LN.PL[1].ammo_capacity = 6;
__LN.PL[1].reload_time = 15 * 6
__LN.PL[1].shot_delay = 6
__LN.PL[2].shell_name = {"M256_120_HE_L55"};
__LN.PL[2].ammo_capacity = 11;
__LN.PL[2].reload_time = 15 * 11
__LN.PL[2].shot_delay = 10
__LN.PL[1].virtualStwID = 1;
__LN.PL[2].virtualStwID = 2;
__LN.sightMasterMode = 1;
__LN.sightIndicationMode = 2;

--GT.WS[1].LN[3]
__LN = add_launcher(GT.WS[ws], GT_t.LN_t.machinegun_MG3);
set_recursive_metatable(__LN.sensor, GT_t.WSN_t[7]);
__LN.beamWidth = math.rad(1);
__LN.BR[1].connector_name = 'POINT_MG_01';
__LN.sightMasterMode = 1;
__LN.sightIndicationMode = 3;
__LN.customViewPoint = { "XLHL-60/HL-60", {0.1, 2.7, 0.0}};
for i=3,10 do
    __LN.PL[i] = {};
    set_recursive_metatable(__LN.PL[i], __LN.PL[1]);
end;


GT.WS[1].LN[4] = {}
__LN = GT.WS[ws].LN[4]
__LN.name = "CMD_Periscope"
__LN.display_name = _("Commander Periscope Sight")
__LN.type = 103
__LN.distanceMin = 0
__LN.distanceMax = 0
__LN.distanceMaxForFCS = 5000
__LN.BR = {{connector_name = 'PNT_SIGHT_CMD'}}
__LN.customViewPoint = { "CWS/CWS", {0.1, 2.7, 0.0} }










--GT.WS[2].LN[2]
ws = GT_t.inc_ws();
GT.WS[ws] = {};
GT.WS[ws].center = 'CENTER_MG_02';
GT.WS[ws].angles = {
                    {math.rad(180), math.rad(-180), math.rad(-9), math.rad(50)},
                    };
GT.WS[ws].drawArgument1 = 24;
GT.WS[ws].drawArgument2 = 25;
GT.WS[ws].omegaY = math.rad(60);
GT.WS[ws].omegaZ = math.rad(60);
GT.WS[ws].pidY = MG_TOWER_PIDY
GT.WS[ws].pidZ = MG_TOWER_PIDZ
GT.WS[ws].stabilizer = true;
GT.WS[ws].laser = true;


__LN = add_launcher(GT.WS[ws], GT_t.LN_t.machinegun_MG3);
set_recursive_metatable(__LN.sensor, GT_t.WSN_t[2]);
__LN.type = 10;
__LN.beamWidth = math.rad(1);
__LN.BR[1].connector_name = 'POINT_MG_02';
__LN.customViewPoint = { "XLHL-60/HL-60", {0.1, 2.7, 0.0}};
for i=2,10 do
    __LN.PL[i] = {};
    set_recursive_metatable(__LN.PL[i], __LN.PL[1]);
end;
------------------------------------------------------------------------------------------
ws = GT_t.inc_ws(); --Second turret, which contains the commander optic, the 2 rockets smoke

GT.WS[ws] = {};
GT.WS[ws].base = 1;
GT.WS[ws].center = 'CENTER_TOWER2';
GT.WS[ws].angles = {
                    {math.rad(180), math.rad(-180), math.rad(-9), math.rad(40)},
                    };
GT.WS[ws].drawArgument1 = 25; --Arguments of the second turret, a second turret must use arguments from 25, don't give it arg 2 arg 3, it won't work, it must be 25-26, then 27-28 etc etc
GT.WS[ws].drawArgument2 = 26;
GT.WS[ws].omegaY = math.rad(90);
GT.WS[ws].omegaZ = math.rad(90);
GT.WS[ws].laser = true;
GT.WS[ws].stabilizer = true;
GT.WS[ws].pidY = {p=40,i=1,d=7,inn=5,}; --{p=100,i=0.1,d=12,inn=50,};
GT.WS[ws].pidZ = {p=40,i=1,d=7,inn=5,};
GT.WS[ws].pointer = 'POINT_CDB'
GT.WS[ws].stabilizer = true;
GT.WS[ws].laser = true;


--GT.WS[1].LN[1]
__LN = add_launcher(GT.WS[ws], GT_t.LN_t.tank_gun_120mm);
__LN.beamWidth = math.rad(1);
__LN.BR[1] = {connector_name = 'POINT_GUN_01',
			recoilArgument = 23,
			recoilTime = 0.3};
__LN.PL[1].shell_name = {"M256_120_AP_L55"};
__LN.PL[1].ammo_capacity = 9
__LN.PL[1].reload_time = 15 * 9
__LN.PL[1].shot_delay = 6
__LN.PL[2].shell_name = {"M256_120_AP_L55"};
__LN.PL[2].ammo_capacity = 16
__LN.PL[2].reload_time = 15 * 16
__LN.PL[2].shot_delay = 10
__LN.PL[1].virtualStwID = 1;
__LN.PL[2].virtualStwID = 2;
__LN.sightMasterMode = 1;
__LN.sightIndicationMode = 1;
--GT.WS[1].LN[2]
__LN = add_launcher(GT.WS[ws], __LN); -- HE gun
__LN.type = 6;
__LN.distanceMin = 20;
__LN.distanceMax = 8000;
__LN.PL[1].shell_name = {"M256_120_HE_L55"};
__LN.PL[1].ammo_capacity = 6;
__LN.PL[1].reload_time = 15 * 6
__LN.PL[1].shot_delay = 6
__LN.PL[2].shell_name = {"M256_120_HE_L55"};
__LN.PL[2].ammo_capacity = 11;
__LN.PL[2].reload_time = 15 * 11
__LN.PL[2].shot_delay = 10
__LN.PL[1].virtualStwID = 1;
__LN.PL[2].virtualStwID = 2;
__LN.sightMasterMode = 1;
__LN.sightIndicationMode = 2;


-----------------------------------------------------------------------------------------------------------

-- 高机
ws = GT_t.inc_ws()
GT.WS[ws] = {}
GT.WS[ws].base = 1
GT.WS[ws].center = 'CENTER_MGUN'
GT.WS[ws].angles = {
    {math.rad(180), math.rad(-180), math.rad(-8), math.rad(63)},
}
GT.WS[ws].drawArgument1 = 25
GT.WS[ws].drawArgument2 = 26
GT.WS[ws].omegaY = math.rad(80)
GT.WS[ws].omegaZ = math.rad(60)
GT.WS[ws].pidY = {p=100,i=0.1,d=12,inn=50,}
GT.WS[ws].pidZ = {p=100,i=0.1,d=12,inn=50,}
GT.WS[ws].stabilizer = true;
GT.WS[ws].laser = true;


__LN = add_launcher(GT.WS[ws], GT_t.LN_t.machinegun_MG3,GT_t.LN_t.tank_gun_120mm,__LN)
__LN.type = 10 -- AA machinegun
__LN.PL = {{}, {}}
set_recursive_metatable(__LN.PL[1], GT_t.LN_t.machinegun_MG3.PL[1])
__LN.PL[1].ammo_capacity = 150
__LN.PL[1].switch_delay  = 15
set_recursive_metatable(__LN.PL[2], __LN.PL[1])
__LN.BR[1].connector_name = 'PNT_MGUN'
__LN.fireAnimationArgument = 44
__LN.customViewPoint = { "CWS/CWS", {-1.6, 2.7, -0.06} }
__LN.customViewPoint = { "XLHL-60/HL-60", {-1.6, 2.7, -0.06}};
__LN.sightMasterMode = 1
__LN.distanceMaxForFCS = 4000
__LN.customViewPoint = { "XLHL-60/HL-60", {-1.6, 2.7, -0.06}};



GT.WS[ws].LN[2] = {}
__LN = GT.WS[ws].LN[2]
__LN.name = "CMD_Periscope"
__LN.display_name = _("Commander Periscope Sight")
__LN.type = 103
__LN.distanceMin = 0
__LN.distanceMax = 0
__LN.distanceMaxForFCS = 5000
__LN.BR = {{connector_name = 'PNT_SIGHT_CMD'}}
__LN.customViewPoint = { "CWS/CWS", {-1.6, 2.7, -0.06} }
---------------------------------------------------------------------------------------
ws = GT_t.inc_ws(); --Second turret, which contains the commander optic, the 2 rockets smoke
GT.WS[ws] = {};
GT.WS[ws].base = 1;
GT.WS[ws].center = 'CENTER_TOWER2';
GT.WS[ws].angles = {
                    {math.rad(180), math.rad(-180), math.rad(-9), math.rad(40)},
                    };
GT.WS[ws].drawArgument1 = 25; --Arguments of the second turret, a second turret must use arguments from 25, don't give it arg 2 arg 3, it won't work, it must be 25-26, then 27-28 etc etc
GT.WS[ws].drawArgument2 = 26;
GT.WS[ws].omegaY = math.rad(90);
GT.WS[ws].omegaZ = math.rad(90);
GT.WS[ws].laser = true;
GT.WS[ws].stabilizer = true;
GT.WS[ws].pidY = {p=40,i=1,d=7,inn=5,}; --{p=100,i=0.1,d=12,inn=50,};
GT.WS[ws].pidZ = {p=40,i=1,d=7,inn=5,};
GT.WS[ws].pointer = 'POINT_CDB'
GT.WS[ws].pointer = 'vsusp'
GT.WS[ws].stabilizer = true;
GT.WS[ws].laser = true;


__LN = add_launcher(GT.WS[ws], GT_t.LN_t.PKT); --Machin gun 
__LN.fireAnimationArgument = 125
__LN.beamWidth = math.rad(1);
__LN.BR[1] = {connector_name = 'POINT_AANF1',
			  recoilArgument = 24,
			  recoilTime = 60/1800}
__LN.BR[1].recoilArgument = 24
__LN.customViewPoint = { 'XLCDB/GPS', {-1.6, 2.7, -0.06}};
__LN.sightMasterMode = 1
__LN = nil; --End of all of this
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


GT.Name = "Leopard-2";
GT.DisplayName = _("MBT Leopard-2A6M");
GT.DisplayNameShort = _("Leo-2");
GT.Rate = 20;

GT.Sensors = { OPTIC = {"EMES 15 day", "EMES 15 night",
                        --"PERI-R17A2 day", "PERI-R17A2 night",
                        },
            };

GT.DetectionRange  = 0;
GT.airWeaponDist = 1500
GT.ThreatRange =  GT.WS[1].LN[1].distanceMax;
GT.mapclasskey = "P0091000001";
GT.attribute = {wsType_Ground,wsType_Tank,wsType_Gun,WSTYPE_PLACEHOLDER,
                "Tanks",
                "Modern Tanks",
                };
GT.Countries = {"Germany"}
GT.category = "Armor";
GT.tags  =
{
    "Armor",
	"MBT",
}
