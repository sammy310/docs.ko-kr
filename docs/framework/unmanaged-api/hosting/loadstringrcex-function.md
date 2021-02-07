---
description: '자세히 알아보기: LoadStringRCEx 함수'
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
ms.openlocfilehash: d3fe4b97014e5093dd8d209a5e27bac4ed7b879f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679918"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="6c031-103">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="6c031-103">LoadStringRCEx Function</span></span>

<span data-ttu-id="6c031-104">HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-104">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="6c031-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c031-106">구문</span><span class="sxs-lookup"><span data-stu-id="6c031-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6c031-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c031-107">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="6c031-108">진행 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-108">[in] A culture identifier.</span></span> <span data-ttu-id="6c031-109">에 대해-1 `lcid` 을 전달 하 여 기본 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-109">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="6c031-110">진행 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-110">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="6c031-111">제한이 성공적으로 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-111">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="6c031-112">진행 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-112">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="6c031-113">진행 무시.</span><span class="sxs-lookup"><span data-stu-id="6c031-113">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="6c031-114">제한이 오류 메시지의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-114">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c031-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="6c031-115">Return Value</span></span>  

 <span data-ttu-id="6c031-116">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-116">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="6c031-117">반환 코드</span><span class="sxs-lookup"><span data-stu-id="6c031-117">Return code</span></span>|<span data-ttu-id="6c031-118">설명</span><span class="sxs-lookup"><span data-stu-id="6c031-118">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6c031-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c031-119">S_OK</span></span>|<span data-ttu-id="6c031-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="6c031-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6c031-121">E_INVALIDARG</span></span>|<span data-ttu-id="6c031-122">`szBuffer` 가 null 이거나 `iMax` 가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-122">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c031-123">설명</span><span class="sxs-lookup"><span data-stu-id="6c031-123">Remarks</span></span>  

 <span data-ttu-id="6c031-124">메서드가 성공적으로 완료 되지 않으면에 `szBuffer` 빈 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c031-124">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c031-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c031-125">Requirements</span></span>  

 <span data-ttu-id="6c031-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c031-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c031-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6c031-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c031-128">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c031-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c031-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c031-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c031-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c031-130">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6c031-131">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="6c031-131">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="6c031-132">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="6c031-132">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
