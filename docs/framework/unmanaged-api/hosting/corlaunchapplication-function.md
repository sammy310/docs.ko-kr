---
description: '다음에 대 한 자세한 정보: CorLaunchApplication 함수'
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
ms.openlocfilehash: 89f1f37ddde69fb5ecc24fd9dfd0d0c27d5fac40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716954"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="98dac-103">CorLaunchApplication 함수</span><span class="sxs-lookup"><span data-stu-id="98dac-103">CorLaunchApplication Function</span></span>

<span data-ttu-id="98dac-104">지정 된 매니페스트 및 기타 응용 프로그램 데이터를 사용 하 여 지정 된 네트워크 경로에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-104">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="98dac-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98dac-106">구문</span><span class="sxs-lookup"><span data-stu-id="98dac-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="98dac-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98dac-107">Parameters</span></span>  

 `dwClickOnceHost`  
 <span data-ttu-id="98dac-108">진행 응용 프로그램을 시작 하는 호스트의 유형을 지정 하는 [HOST_TYPE](host-type-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-108">[in] A value of the [HOST_TYPE](host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="98dac-109">진행 시작 되는 응용 프로그램의 전체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-109">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="98dac-110">진행 응용 프로그램에 대 한 매니페스트 경로 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-110">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="98dac-111">진행 시작 중인 응용 프로그램에 대 한 매니페스트의 경로를 지정 하는 문자열의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-111">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="98dac-112">진행 시작 중인 응용 프로그램에 대 한 활성화 데이터 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-112">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="98dac-113">진행 시작 중인 응용 프로그램에 대 한 활성화 데이터 항목인 각각의 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-113">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="98dac-114">제한이 응용 프로그램이 로드 된 프로세스에 대 한 정보에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="98dac-114">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98dac-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98dac-115">Requirements</span></span>  

 <span data-ttu-id="98dac-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98dac-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98dac-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="98dac-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98dac-118">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98dac-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98dac-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98dac-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98dac-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98dac-120">See also</span></span>

- [<span data-ttu-id="98dac-121">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="98dac-121">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
