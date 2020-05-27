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
ms.openlocfilehash: a05cbe985c2cfebb67756fdfb54398b36e87f441
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008518"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="f9817-102">LoadStringRCEx 함수</span><span class="sxs-lookup"><span data-stu-id="f9817-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="f9817-103">HRESULT 값을 지정 된 문화권에 대 한 적절 한 오류 메시지로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="f9817-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9817-105">구문</span><span class="sxs-lookup"><span data-stu-id="f9817-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f9817-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9817-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="f9817-107">진행 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-107">[in] A culture identifier.</span></span> <span data-ttu-id="f9817-108">에 대해-1 `lcid` 을 전달 하 여 기본 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="f9817-109">진행 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="f9817-110">제한이 성공적으로 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="f9817-111">진행 오류 메시지 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="f9817-112">진행 무시.</span><span class="sxs-lookup"><span data-stu-id="f9817-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="f9817-113">제한이 오류 메시지의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9817-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="f9817-114">Return Value</span></span>  
 <span data-ttu-id="f9817-115">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="f9817-116">반환 코드</span><span class="sxs-lookup"><span data-stu-id="f9817-116">Return code</span></span>|<span data-ttu-id="f9817-117">Description</span><span class="sxs-lookup"><span data-stu-id="f9817-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f9817-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9817-118">S_OK</span></span>|<span data-ttu-id="f9817-119">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="f9817-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f9817-120">E_INVALIDARG</span></span>|<span data-ttu-id="f9817-121">`szBuffer`가 null 이거나 `iMax` 가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9817-122">설명</span><span class="sxs-lookup"><span data-stu-id="f9817-122">Remarks</span></span>  
 <span data-ttu-id="f9817-123">메서드가 성공적으로 완료 되지 않으면에 `szBuffer` 빈 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9817-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9817-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9817-124">Requirements</span></span>  
 <span data-ttu-id="f9817-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9817-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9817-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f9817-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9817-127">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f9817-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9817-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9817-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9817-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9817-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f9817-130">LoadStringRC 함수</span><span class="sxs-lookup"><span data-stu-id="f9817-130">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="f9817-131">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="f9817-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
