---
title: CorLaunchApplication 함수
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c997ab107ba3ceb7773bc9235b9c9dcd4d97df8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985792"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="a13ac-102">CorLaunchApplication 함수</span><span class="sxs-lookup"><span data-stu-id="a13ac-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="a13ac-103">지정한 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="a13ac-104">이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13ac-105">구문</span><span class="sxs-lookup"><span data-stu-id="a13ac-105">Syntax</span></span>  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a13ac-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a13ac-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="a13ac-107">[in] 값을 [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) 응용 프로그램을 시작 하는 호스트의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="a13ac-108">[in] 실행 하는 응용 프로그램의 전체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="a13ac-109">[in] 응용 프로그램에 대 한 매니페스트 경로의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="a13ac-110">[in] 실행 하는 응용 프로그램에 대 한 매니페스트 경로 지정 하는 각 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="a13ac-111">[in] 실행 하는 응용 프로그램에 대 한 활성화 데이터 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="a13ac-112">[in] 실행 하는 응용 프로그램에 대 한 활성화 데이터 항목은 각 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="a13ac-113">[out] 응용 프로그램을 로드 하는 프로세스에 대 한 정보에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a13ac-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13ac-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a13ac-114">Requirements</span></span>  
 <span data-ttu-id="a13ac-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a13ac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13ac-116">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a13ac-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a13ac-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a13ac-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a13ac-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13ac-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13ac-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="a13ac-119">See also</span></span>

- [<span data-ttu-id="a13ac-120">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="a13ac-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
