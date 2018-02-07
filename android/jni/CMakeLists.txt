cmake_minimum_required(VERSION 3.4.1)

project(ARToolkit C)

set(ARTOOLKIT_ROOT ${CMAKE_CURRENT_LIST_DIR}/../../)
set(ARTOOLKIT_INCLUDES
    ${ARTOOLKIT_ROOT}/include
    ${ARTOOLKIT_ROOT}/include/android
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher)
include_directories(${ARTOOLKIT_INCLUDES})

add_library(ar STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/ar3DCreateHandle.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/ar3DUtil.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arCreateHandle.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arDetectMarker.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arDetectMarker2.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arFilterTransMat.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arGetLine.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arGetMarkerInfo.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arGetTransMat.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arGetTransMatStereo.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arImageProc.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabeling.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubDBIC.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubDBRC.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubDBZ.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubDWIC.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubDWRC.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubDWZ.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubEBIC.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubEBRC.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubEBZ.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubEWIC.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubEWRC.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arLabelingSub/arLabelingSubEWZ.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arPattAttach.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arPattCreateHandle.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arPattGetID.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arPattLoad.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arPattSave.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/arUtil.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mAlloc.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mAllocDup.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mAllocInv.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mAllocMul.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mAllocTrans.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mAllocUnit.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mDet.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mDisp.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mDup.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mFree.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mInv.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mMul.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mPCA.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mSelfInv.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mTrans.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/mUnit.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramChangeSize.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramClear.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramDecomp.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramDisp.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramDistortion.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramFile.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramGL.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramGetPerspective.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/paramLT.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/vAlloc.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/vDisp.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/vFree.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/vHouse.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/vInnerP.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR/vTridiag.c)
set_target_properties(ar PROPERTIES LINKER_LANGUAGE C)
target_link_libraries(ar aricp)

add_library(aricp STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpCalibStereo.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpCore.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpHandle.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpPoint.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpPointRobust.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpStereoHandle.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpStereoPoint.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpStereoPointRobust.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARICP/icpUtil.c)
set_target_properties(aricp PROPERTIES LINKER_LANGUAGE C)
target_link_libraries(aricp ar)

add_library(armulti STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/ARMulti/arMultiFreeConfig.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARMulti/arMultiGetTransMat.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARMulti/arMultiGetTransMatStereo.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARMulti/arMultiReadConfigFile.c)
set_target_properties(armulti PROPERTIES LINKER_LANGUAGE C)

add_library(argsub_es STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/Gl/gsub_es.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Gl/glStateCache.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Gl/gsub_mtx.c)
set_target_properties(argsub_es PROPERTIES LINKER_LANGUAGE C)

add_library(argsub_es2 STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/Gl/gsub_es2.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Gl/glStateCache2.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Gl/gsub_mtx.c)
set_target_properties(argsub_es2 PROPERTIES LINKER_LANGUAGE C)

add_library(arosg STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/ARosg/arosg.cpp)
set_target_properties(arosg PROPERTIES LINKER_LANGUAGE C)

add_library(eden STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/EdenError.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/EdenGLFont.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/EdenMath.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/EdenMessage.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/EdenSound.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/EdenSurfaces.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/EdenTime.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/EdenUtil.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/glm.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/readtex.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/ALFramework.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/CWaves.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_8x13.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_9x15.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_bitmap.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_bwidth.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_hel10.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_hel12.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_hel18.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_mroman.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_roman.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_stroke.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_swidth.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_tr10.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Eden/gluttext/glut_tr24.c)
set_target_properties(eden PROPERTIES LINKER_LANGUAGE C)

add_library(kpm STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/detectors/DoG_scale_invariant_detector.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/detectors/gaussian_scale_space_pyramid.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/detectors/gradients.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/detectors/harris.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/detectors/orientation_assignment.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/detectors/pyramid.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/facade/visual_database_facade.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/framework/date_time.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/framework/image.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/framework/logger.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/framework/timers.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/matchers/freak.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/FreakMatcher/matchers/hough_similarity_voting.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/kpmFopen.c
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/kpmHandle.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/kpmMatching.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/kpmRefDataSet.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/kpmResult.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/KPM/kpmUtil.cpp)

add_library(ar2 STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/coord.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/featureMap.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/featureSet.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/handle.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/imageSet.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/jpeg.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/marker.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/matching.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/matching2.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/searchPoint.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/selectTemplate.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/surface.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/template.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/tracking.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/tracking2d.c
    ${ARTOOLKIT_ROOT}/lib/SRC/AR2/util.c)
set_target_properties(ar2 PROPERTIES LINKER_LANGUAGE C)

add_library(arutil STATIC
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/android_system_property_get.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/crypt.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/file_utils.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/ioapi.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/log.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/nftw.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/profile.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/system.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/thread_sub.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/time.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/unzip.c
    ${ARTOOLKIT_ROOT}/lib/SRC/ARUtil/zip.c)
set_target_properties(arutil PROPERTIES LINKER_LANGUAGE C)

add_library(arvideo STATIC
    # ${ARTOOLKIT_ROOT}/lib/SRC/Video/AVFoundation/cparams.c
    # ${ARTOOLKIT_ROOT}/lib/SRC/Video/Android/sqlite3.c
    # ${ARTOOLKIT_ROOT}/lib/SRC/Video/Android/videoAndroid.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/Dummy/videoDummy.c
    # ${ARTOOLKIT_ROOT}/lib/SRC/Video/GStreamer/videoGStreamer.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/Image/videoImage.c
    # ${ARTOOLKIT_ROOT}/lib/SRC/Video/Video4Linux2/videoV4L2.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/cparamSearch.c
    # ${ARTOOLKIT_ROOT}/lib/SRC/Video/libdc1394/video1394.c
    # ${ARTOOLKIT_ROOT}/lib/SRC/Video/libdc1394/video1394Format.c
    # ${ARTOOLKIT_ROOT}/lib/SRC/Video/libdc1394/video1394Setting.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/nxjson.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/video.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/video2.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/videoAspectRatio.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/videoLuma.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/videoRGBA.c
    ${ARTOOLKIT_ROOT}/lib/SRC/Video/videoSaveImage.c)
set_target_properties(arvideo PROPERTIES LINKER_LANGUAGE C)

set(CURL_ROOT ${ARTOOLKIT_ROOT}/android/jni/curl)
add_library(curl STATIC IMPORTED)
set_target_properties(curl PROPERTIES IMPORTED_LOCATION ${CURL_ROOT}/libs/${ANDROID_ABI}/libcurl.a)
include_directories(${CURL_ROOT}/include)

find_library(log-lib log)
find_library(gl-lib GLESv1_CM)
find_library(z-lib z)
find_library(curl-lib curl)

include(AndroidNdkModules)
android_ndk_import_module_cpufeatures()
set_target_properties(cpufeatures PROPERTIES LINKER_LANGUAGE C)

add_library(ARWrapper SHARED
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ARController.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ARMarker.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ARMarkerMulti.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ARMarkerNFT.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ARMarkerSquare.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ARPattern.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ARToolKitWrapperExportedAPI.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ARVideoSource.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/AndroidFeatures.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/ColorConversion.cpp
    ${ARTOOLKIT_ROOT}/lib/SRC/ARWrapper/trackingSub.c)
set_target_properties(ARWrapper PROPERTIES LINKER_LANGUAGE C)
target_link_libraries(ARWrapper
    ${log-lib}
    ${gl-lib}
    ${z-lib}
    ar
    ar2
    kpm
    argsub_es
    armulti
    aricp
    arvideo
    arutil
    cpufeatures
    curl)

# target_include_directories(ar INTERFACE ${ARTOOLKIT_ROOT}/include)