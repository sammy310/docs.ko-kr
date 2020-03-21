---
title: GetVersionFromProcess 함수
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: a04a0c5e6865c3664d2cb5fb341c3625e35d4d7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178125"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="3d269-102">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="3d269-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="3d269-103">지정된 프로세스 핸들과 연결된 공통 언어 런타임(CLR)의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="3d269-104">이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d269-105">구문</span><span class="sxs-lookup"><span data-stu-id="3d269-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d269-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d269-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="3d269-107">【인】 프로세스에 대한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="3d269-108">【아웃】 메서드가 성공적으로 완료되면 버전 번호 문자열이 포함된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3d269-109">【인】 버전 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="3d269-110">【아웃】 버전 번호 문자열의 길이에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d269-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="3d269-111">Return Value</span></span>  
 <span data-ttu-id="3d269-112">이 메서드는 다음 값 외에 WinError.h에 정의된 표준 구성 요소 개체 모델(COM) 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="3d269-113">반환 코드</span><span class="sxs-lookup"><span data-stu-id="3d269-113">Return code</span></span>|<span data-ttu-id="3d269-114">Description</span><span class="sxs-lookup"><span data-stu-id="3d269-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3d269-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d269-115">S_OK</span></span>|<span data-ttu-id="3d269-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="3d269-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3d269-117">E_INVALIDARG</span></span>|<span data-ttu-id="3d269-118">`pVersion`null이며 `cchBuffer` null이 아니거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="3d269-119">또는</span><span class="sxs-lookup"><span data-stu-id="3d269-119">-or-</span></span><br /><br /> <span data-ttu-id="3d269-120">`hProcess`프로세스에 대한 올바른 핸들이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="3d269-121">또는</span><span class="sxs-lookup"><span data-stu-id="3d269-121">-or-</span></span><br /><br /> <span data-ttu-id="3d269-122">CLR이 로드되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="3d269-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="3d269-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="3d269-124">`cchBuffer`은 null 또는 버전 문자열의 길이보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="3d269-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3d269-125">E_NOTIMPL</span></span>|<span data-ttu-id="3d269-126">이 방법은 마이크로 소프트 윈도우 95, 마이크로 소프트 윈도우 98, 또는 마이크로 소프트 윈도우 밀레니엄 에디션 운영 체제에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d269-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d269-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d269-127">Requirements</span></span>  
 <span data-ttu-id="3d269-128">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d269-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d269-129">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="3d269-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d269-130">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3d269-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d269-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d269-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d269-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d269-132">See also</span></span>

- [<span data-ttu-id="3d269-133">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="3d269-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="3d269-134">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="3d269-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="3d269-135">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="3d269-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
