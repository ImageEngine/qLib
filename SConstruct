import os
import IEEnv
import glob

import VersionControl
VersionControl.setVersion('IEBuild', '6.15.1')
import IEBuild

majorVersion = '0'
minorVersion = '2'
patchVersion = '5'
version = '.'.join( [ majorVersion, minorVersion, patchVersion ] )

###############################################################################
# Install OTLs
###############################################################################

otls = glob.glob( "otls/base/*" )
for otl in otls :
	IEBuild.HoudiniOTL(
		ARGUMENTS,
		otl,
	).finalize()

###############################################################################
# Install the toolbar
###############################################################################

IEBuild.HoudiniGeneric(
	ARGUMENTS,
	"toolbar/qLib.shelf",
	version,
	installPathExtension = "toolbar",
	versionedFileName = False
).finalize()

###############################################################################
# installAll
###############################################################################

IEBuild.InstallAll(
	{
		"HOUDINI_VERSION": "active",
	},
).finalize()
