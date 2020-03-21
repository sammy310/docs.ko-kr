---
title: NextMethod 함수(관리되지 않는 API 참조)
description: NextMethod 함수는 열거형에서 다음 메서드를 검색합니다.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174929"
---
# <a name="nextmethod-function"></a><span data-ttu-id="3a53c-103">NextMethod 함수</span><span class="sxs-lookup"><span data-stu-id="3a53c-103">NextMethod function</span></span>
<span data-ttu-id="3a53c-104">[BeginMethod Enumeration에](beginmethodenumeration.md)대 한 호출로 시작 하는 열거형에서 다음 메서드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3a53c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a53c-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="3a53c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a53c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3a53c-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3a53c-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="3a53c-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-109">[in] Reserved.</span></span> <span data-ttu-id="3a53c-110">이 매개변수는 0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="3a53c-111">【아웃】 호출 하기 전에 `null` 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="3a53c-112">함수가 반환되면 메서드 이름이 `BSTR` 포함된 새 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="3a53c-113">【아웃】 메서드에 대 한 매개 변수를 포함 하는 [IWbemClassObject에](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 대 한 포인터를 `in` 받는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="3a53c-114">【아웃】 메서드에 대 한 매개 변수를 포함 하는 [IWbemClassObject에](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 대 한 포인터를 `out` 받는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="3a53c-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="3a53c-115">Return value</span></span>

<span data-ttu-id="3a53c-116">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3a53c-117">지속적임</span><span class="sxs-lookup"><span data-stu-id="3a53c-117">Constant</span></span>  |<span data-ttu-id="3a53c-118">값</span><span class="sxs-lookup"><span data-stu-id="3a53c-118">Value</span></span>  |<span data-ttu-id="3a53c-119">Description</span><span class="sxs-lookup"><span data-stu-id="3a53c-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="3a53c-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="3a53c-120">0x8004101d</span></span> | <span data-ttu-id="3a53c-121">함수에 대한 호출이 [`BeginEnumeration`](beginenumeration.md) 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3a53c-122">0</span><span class="sxs-lookup"><span data-stu-id="3a53c-122">0</span></span> | <span data-ttu-id="3a53c-123">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="3a53c-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="3a53c-124">0x40005</span></span> | <span data-ttu-id="3a53c-125">열거형에는 더 이상 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3a53c-126">설명</span><span class="sxs-lookup"><span data-stu-id="3a53c-126">Remarks</span></span>

<span data-ttu-id="3a53c-127">이 함수는 [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="3a53c-128">호출자는 [BeginMethodEnumeration](beginmethodenumeration.md) 함수를 호출하여 열거 시퀀스를 시작한 다음 함수가 반환될 `WBEM_S_NO_MORE_DATA`때까지 [NextMethod] 함수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="3a53c-129">선택적으로 호출자는 [EndMethodEnumeration을](endmethodenumeration.md)호출하여 시퀀스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="3a53c-130">호출자는 언제든지 [EndMethodEnmeration을](endmethodenumeration.md) 호출하여 열거를 조기에 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a53c-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="3a53c-131">예제</span><span class="sxs-lookup"><span data-stu-id="3a53c-131">Example</span></span>

<span data-ttu-id="3a53c-132">C++ 예제는 [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 메서드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3a53c-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a53c-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a53c-133">Requirements</span></span>  
 <span data-ttu-id="3a53c-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a53c-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a53c-135">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3a53c-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3a53c-136">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3a53c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a53c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a53c-137">See also</span></span>

- [<span data-ttu-id="3a53c-138">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3a53c-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
