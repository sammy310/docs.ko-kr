---
title: LoadStringRCEx 함수
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: 68332aee895f012bcf6ab6a72936c8dddc7f28a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122041"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="32d9d-102">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="32d9d-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="32d9d-103">HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="32d9d-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d9d-105">구문</span><span class="sxs-lookup"><span data-stu-id="32d9d-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32d9d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32d9d-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="32d9d-107">진행 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-107">[in] A culture identifier.</span></span> <span data-ttu-id="32d9d-108">기본 문화권을 사용 하려면-`lcid` 1을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="32d9d-109">진행 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="32d9d-110">제한이 성공적으로 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="32d9d-111">진행 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="32d9d-112">진행 무시.</span><span class="sxs-lookup"><span data-stu-id="32d9d-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="32d9d-113">제한이 오류 메시지의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32d9d-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="32d9d-114">Return Value</span></span>  
 <span data-ttu-id="32d9d-115">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="32d9d-116">반환 코드</span><span class="sxs-lookup"><span data-stu-id="32d9d-116">Return code</span></span>|<span data-ttu-id="32d9d-117">설명</span><span class="sxs-lookup"><span data-stu-id="32d9d-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="32d9d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="32d9d-118">S_OK</span></span>|<span data-ttu-id="32d9d-119">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="32d9d-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="32d9d-120">E_INVALIDARG</span></span>|<span data-ttu-id="32d9d-121">`szBuffer` null 이거나 `iMax` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32d9d-122">주의</span><span class="sxs-lookup"><span data-stu-id="32d9d-122">Remarks</span></span>  
 <span data-ttu-id="32d9d-123">메서드가 성공적으로 완료 되지 않으면 `szBuffer`에 빈 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32d9d-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d9d-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32d9d-124">Requirements</span></span>  
 <span data-ttu-id="32d9d-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32d9d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d9d-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="32d9d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32d9d-127">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="32d9d-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32d9d-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d9d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d9d-129">참조</span><span class="sxs-lookup"><span data-stu-id="32d9d-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="32d9d-130">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="32d9d-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="32d9d-131">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="32d9d-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
