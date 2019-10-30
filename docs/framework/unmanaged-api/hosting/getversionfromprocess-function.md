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
ms.openlocfilehash: 76c033b11f3212241827d74f4fe18ee881f20b64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127045"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="fe9a5-102">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="fe9a5-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="fe9a5-103">지정 된 프로세스 핸들과 연결 된 CLR (공용 언어 런타임)의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="fe9a5-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe9a5-105">구문</span><span class="sxs-lookup"><span data-stu-id="fe9a5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe9a5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe9a5-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="fe9a5-107">진행 프로세스에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="fe9a5-108">제한이 메서드가 성공적으로 완료 되 면 버전 번호 문자열이 포함 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="fe9a5-109">진행 버전 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="fe9a5-110">제한이 버전 번호 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe9a5-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="fe9a5-111">Return Value</span></span>  
 <span data-ttu-id="fe9a5-112">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="fe9a5-113">반환 코드</span><span class="sxs-lookup"><span data-stu-id="fe9a5-113">Return code</span></span>|<span data-ttu-id="fe9a5-114">설명</span><span class="sxs-lookup"><span data-stu-id="fe9a5-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fe9a5-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe9a5-115">S_OK</span></span>|<span data-ttu-id="fe9a5-116">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="fe9a5-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fe9a5-117">E_INVALIDARG</span></span>|<span data-ttu-id="fe9a5-118">`pVersion` null이 고 `cchBuffer`가 null이 아니거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="fe9a5-119">또는</span><span class="sxs-lookup"><span data-stu-id="fe9a5-119">-or-</span></span><br /><br /> <span data-ttu-id="fe9a5-120">`hProcess`는 프로세스에 대 한 유효한 핸들이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="fe9a5-121">또는</span><span class="sxs-lookup"><span data-stu-id="fe9a5-121">-or-</span></span><br /><br /> <span data-ttu-id="fe9a5-122">CLR이 로드 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="fe9a5-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="fe9a5-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="fe9a5-124">`cchBuffer`가 null 이거나 버전 문자열의 길이 보다 작은 경우</span><span class="sxs-lookup"><span data-stu-id="fe9a5-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="fe9a5-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fe9a5-125">E_NOTIMPL</span></span>|<span data-ttu-id="fe9a5-126">이 방법은 Microsoft windows 95, Microsoft Windows 98 또는 Microsoft Windows Millennium Edition 운영 체제에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe9a5-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe9a5-127">Requirements</span></span>  
 <span data-ttu-id="fe9a5-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe9a5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe9a5-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fe9a5-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe9a5-130">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fe9a5-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe9a5-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe9a5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe9a5-132">참조</span><span class="sxs-lookup"><span data-stu-id="fe9a5-132">See also</span></span>

- [<span data-ttu-id="fe9a5-133">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="fe9a5-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="fe9a5-134">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="fe9a5-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="fe9a5-135">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="fe9a5-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
