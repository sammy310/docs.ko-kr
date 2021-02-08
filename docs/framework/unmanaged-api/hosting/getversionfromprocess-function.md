---
description: '자세한 정보: GetVersionFromProcess 함수'
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
ms.openlocfilehash: ab665d2984f79baf049009690b36782528094937
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785252"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="cad3f-103">GetVersionFromProcess 함수</span><span class="sxs-lookup"><span data-stu-id="cad3f-103">GetVersionFromProcess Function</span></span>

<span data-ttu-id="cad3f-104">지정 된 프로세스 핸들과 연결 된 CLR (공용 언어 런타임)의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-104">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="cad3f-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad3f-106">구문</span><span class="sxs-lookup"><span data-stu-id="cad3f-106">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cad3f-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cad3f-107">Parameters</span></span>  

 `hProcess`  
 <span data-ttu-id="cad3f-108">진행 프로세스에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-108">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="cad3f-109">제한이 메서드가 성공적으로 완료 되 면 버전 번호 문자열이 포함 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-109">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="cad3f-110">진행 버전 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="cad3f-111">제한이 버전 번호 문자열의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cad3f-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="cad3f-112">Return Value</span></span>  

 <span data-ttu-id="cad3f-113">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="cad3f-114">반환 코드</span><span class="sxs-lookup"><span data-stu-id="cad3f-114">Return code</span></span>|<span data-ttu-id="cad3f-115">설명</span><span class="sxs-lookup"><span data-stu-id="cad3f-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="cad3f-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="cad3f-116">S_OK</span></span>|<span data-ttu-id="cad3f-117">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="cad3f-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cad3f-118">E_INVALIDARG</span></span>|<span data-ttu-id="cad3f-119">`pVersion` 가 null이 고 `cchBuffer` 가 null이 아니거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-119">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="cad3f-120">또는</span><span class="sxs-lookup"><span data-stu-id="cad3f-120">-or-</span></span><br /><br /> <span data-ttu-id="cad3f-121">`hProcess` 는 프로세스에 대 한 유효한 핸들이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-121">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="cad3f-122">또는</span><span class="sxs-lookup"><span data-stu-id="cad3f-122">-or-</span></span><br /><br /> <span data-ttu-id="cad3f-123">CLR이 로드 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-123">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="cad3f-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="cad3f-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="cad3f-125">`cchBuffer` 가 null 이거나 버전 문자열의 길이 보다 작은 경우</span><span class="sxs-lookup"><span data-stu-id="cad3f-125">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="cad3f-126">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cad3f-126">E_NOTIMPL</span></span>|<span data-ttu-id="cad3f-127">이 방법은 Microsoft windows 95, Microsoft Windows 98 또는 Microsoft Windows Millennium Edition 운영 체제에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cad3f-127">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cad3f-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cad3f-128">Requirements</span></span>  

 <span data-ttu-id="cad3f-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cad3f-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cad3f-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cad3f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cad3f-131">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cad3f-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cad3f-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cad3f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad3f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cad3f-133">See also</span></span>

- [<span data-ttu-id="cad3f-134">GetRequestedRuntimeInfo 함수</span><span class="sxs-lookup"><span data-stu-id="cad3f-134">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="cad3f-135">GetRequestedRuntimeVersion 함수</span><span class="sxs-lookup"><span data-stu-id="cad3f-135">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="cad3f-136">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="cad3f-136">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
