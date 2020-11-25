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
ms.openlocfilehash: 1aa5c9f5dd7dd63e69c2eed1f6dd8ad6f007f01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727538"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="15cde-102">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="15cde-102">LoadStringRCEx Function</span></span>

<span data-ttu-id="15cde-103">HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="15cde-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15cde-105">구문</span><span class="sxs-lookup"><span data-stu-id="15cde-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="15cde-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15cde-106">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="15cde-107">진행 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-107">[in] A culture identifier.</span></span> <span data-ttu-id="15cde-108">에 대해-1 `lcid` 을 전달 하 여 기본 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="15cde-109">진행 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="15cde-110">제한이 성공적으로 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="15cde-111">진행 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="15cde-112">진행 무시.</span><span class="sxs-lookup"><span data-stu-id="15cde-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="15cde-113">제한이 오류 메시지의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15cde-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="15cde-114">Return Value</span></span>  

 <span data-ttu-id="15cde-115">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="15cde-116">반환 코드</span><span class="sxs-lookup"><span data-stu-id="15cde-116">Return code</span></span>|<span data-ttu-id="15cde-117">설명</span><span class="sxs-lookup"><span data-stu-id="15cde-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="15cde-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="15cde-118">S_OK</span></span>|<span data-ttu-id="15cde-119">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="15cde-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="15cde-120">E_INVALIDARG</span></span>|<span data-ttu-id="15cde-121">`szBuffer` 가 null 이거나 `iMax` 가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15cde-122">설명</span><span class="sxs-lookup"><span data-stu-id="15cde-122">Remarks</span></span>  

 <span data-ttu-id="15cde-123">메서드가 성공적으로 완료 되지 않으면에 `szBuffer` 빈 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15cde-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15cde-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15cde-124">Requirements</span></span>  

 <span data-ttu-id="15cde-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15cde-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15cde-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="15cde-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15cde-127">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15cde-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15cde-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15cde-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15cde-129">참조</span><span class="sxs-lookup"><span data-stu-id="15cde-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="15cde-130">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="15cde-130">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="15cde-131">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="15cde-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
