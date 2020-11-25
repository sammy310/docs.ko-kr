---
title: GetObjectText 함수 (관리 되지 않는 API 참조)
description: GetObjectText 함수는 MOF 구문에서 개체의 텍스트 렌더링을 반환 합니다.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ad2b29202222d594cc7976a13929002164314a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718373"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="031cd-103">GetObjectText 함수</span><span class="sxs-lookup"><span data-stu-id="031cd-103">GetObjectText function</span></span>

<span data-ttu-id="031cd-104">MOF (MOF(Managed Object Format)) 구문에서 개체의 텍스트 렌더링을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="031cd-105">구문</span><span class="sxs-lookup"><span data-stu-id="031cd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="031cd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="031cd-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="031cd-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="031cd-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="031cd-109">진행 일반적으로 0입니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-109">[in] Normally 0.</span></span> <span data-ttu-id="031cd-110">`WBEM_FLAG_NO_FLAVORS`(또는 0x1)을 지정 하면 전파 또는 버전 정보 없이 한정자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="031cd-111">`pstrObjectText` 제한이 항목에 대 한 포인터 `null` 입니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="031cd-112">반환 시 `BSTR` 개체의 MOF 구문 렌더링을 포함 하는 새로 할당 된입니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="031cd-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="031cd-113">Return value</span></span>

<span data-ttu-id="031cd-114">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="031cd-115">상수</span><span class="sxs-lookup"><span data-stu-id="031cd-115">Constant</span></span>  |<span data-ttu-id="031cd-116">값</span><span class="sxs-lookup"><span data-stu-id="031cd-116">Value</span></span>  |<span data-ttu-id="031cd-117">설명</span><span class="sxs-lookup"><span data-stu-id="031cd-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="031cd-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="031cd-118">0x80041001</span></span> | <span data-ttu-id="031cd-119">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="031cd-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="031cd-120">0x80041008</span></span> | <span data-ttu-id="031cd-121">매개 변수가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="031cd-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="031cd-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="031cd-122">0x80041006</span></span> | <span data-ttu-id="031cd-123">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="031cd-124">0</span><span class="sxs-lookup"><span data-stu-id="031cd-124">0</span></span> | <span data-ttu-id="031cd-125">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="031cd-126">설명</span><span class="sxs-lookup"><span data-stu-id="031cd-126">Remarks</span></span>

<span data-ttu-id="031cd-127">이 함수는 [IWbemClassObject:: GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="031cd-128">반환 된 MOF 텍스트에는 개체에 대 한 모든 정보가 포함 되어 있지는 않지만 MOF 컴파일러가 원본 개체를 다시 만들 수 있도록 충분 한 정보만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="031cd-129">예를 들어 전파 된 한정자 또는 부모 클래스 속성은 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="031cd-130">다음 알고리즘은 메서드의 매개 변수 텍스트를 다시 생성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="031cd-131">매개 변수는 식별자 값의 순서에 따라 다시 시퀀싱 됩니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="031cd-132">및로 지정 된 매개 변수는 `[in]` `[out]` 단일 매개 변수로 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="031cd-133">`pstrObjectText` 는 함수를 호출할 때에 대 한 포인터 여야 합니다. `null` 포인터가 할당 취소 되지 않으므로 메서드 호출 전에 유효한 문자열을 가리키지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="031cd-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="031cd-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="031cd-134">Requirements</span></span>  

<span data-ttu-id="031cd-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="031cd-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="031cd-136">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="031cd-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="031cd-137">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="031cd-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031cd-138">참조</span><span class="sxs-lookup"><span data-stu-id="031cd-138">See also</span></span>

- [<span data-ttu-id="031cd-139">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="031cd-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
