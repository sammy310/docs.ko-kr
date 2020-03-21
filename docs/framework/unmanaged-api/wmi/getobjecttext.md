---
title: GetObjectText 함수(관리되지 않는 API 참조)
description: GetObjectText 함수는 MOF 구문에서 개체의 텍스트 렌더링을 반환합니다.
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
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176788"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="8f953-103">GetObjectText 함수</span><span class="sxs-lookup"><span data-stu-id="8f953-103">GetObjectText function</span></span>
<span data-ttu-id="8f953-104">MOF(관리되는 개체 형식) 구문에서 개체의 텍스트 렌더링을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8f953-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f953-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="8f953-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f953-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8f953-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8f953-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="8f953-109">【인】 일반적으로 0.</span><span class="sxs-lookup"><span data-stu-id="8f953-109">[in] Normally 0.</span></span> <span data-ttu-id="8f953-110">(또는 0x1)를 지정하면 `WBEM_FLAG_NO_FLAVORS` 한정자가 전파 또는 풍미 정보 없이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="8f953-111">`pstrObjectText`【아웃】 `null` 항목에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="8f953-112">반환시 개체의 MOF 구문 렌더링을 포함 하는 새로 할당 된 `BSTR` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="8f953-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="8f953-113">Return value</span></span>

<span data-ttu-id="8f953-114">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8f953-115">지속적임</span><span class="sxs-lookup"><span data-stu-id="8f953-115">Constant</span></span>  |<span data-ttu-id="8f953-116">값</span><span class="sxs-lookup"><span data-stu-id="8f953-116">Value</span></span>  |<span data-ttu-id="8f953-117">Description</span><span class="sxs-lookup"><span data-stu-id="8f953-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="8f953-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8f953-118">0x80041001</span></span> | <span data-ttu-id="8f953-119">일반적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8f953-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8f953-120">0x80041008</span></span> | <span data-ttu-id="8f953-121">매개 변수가 잘못된 경우</span><span class="sxs-lookup"><span data-stu-id="8f953-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8f953-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8f953-122">0x80041006</span></span> | <span data-ttu-id="8f953-123">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8f953-124">0</span><span class="sxs-lookup"><span data-stu-id="8f953-124">0</span></span> | <span data-ttu-id="8f953-125">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8f953-126">설명</span><span class="sxs-lookup"><span data-stu-id="8f953-126">Remarks</span></span>

<span data-ttu-id="8f953-127">이 함수는 [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="8f953-128">반환된 MOF 텍스트에는 개체에 대한 모든 정보가 포함되지 않지만 MOF 컴파일러가 원래 개체를 다시 만들 수 있는 충분한 정보만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="8f953-129">예를 들어 전파된 한정자 또는 상위 클래스 속성은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="8f953-130">다음 알고리즘은 메서드의 매개 변수의 텍스트를 재구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="8f953-131">매개 변수는 식별자 값의 순서로 순서가 다시 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="8f953-132">단일 매개 변수로 `[in]` `[out]` 지정되고 결합된 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="8f953-133">`pstrObjectText`함수가 호출될 `null` 때의 포인터여야 합니다. 포인터가 할당 할당되지 않으므로 메서드 호출 전에 유효한 문자열을 가리키지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f953-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f953-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f953-134">Requirements</span></span>  
<span data-ttu-id="8f953-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f953-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f953-136">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8f953-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8f953-137">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8f953-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f953-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f953-138">See also</span></span>

- [<span data-ttu-id="8f953-139">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="8f953-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
