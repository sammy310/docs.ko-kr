---
title: NextMethod 함수 (관리 되지 않는 API 참조)
description: NextMethod 함수는 열거형에서 다음 메서드를 검색 합니다.
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
ms.openlocfilehash: 1c20fe5b4a081bd41f51365a36ab5f8f8cfb71ed
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127369"
---
# <a name="nextmethod-function"></a><span data-ttu-id="48db9-103">NextMethod 함수</span><span class="sxs-lookup"><span data-stu-id="48db9-103">NextMethod function</span></span>
<span data-ttu-id="48db9-104">[Beginmethodenumeration](beginmethodenumeration.md)호출로 시작 하는 열거형의 다음 메서드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="48db9-105">구문</span><span class="sxs-lookup"><span data-stu-id="48db9-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="48db9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48db9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="48db9-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="48db9-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="48db9-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-109">[in] Reserved.</span></span> <span data-ttu-id="48db9-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="48db9-111">제한이 호출 이전의 `null`를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="48db9-112">함수가 반환 될 때 메서드 이름이 포함 된 새 `BSTR`의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="48db9-113">제한이 메서드에 대 한 `in` 매개 변수를 포함 하는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 에 대 한 포인터를 받는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="48db9-114">제한이 메서드에 대 한 `out` 매개 변수를 포함 하는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 에 대 한 포인터를 받는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="48db9-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="48db9-115">Return value</span></span>

<span data-ttu-id="48db9-116">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="48db9-117">상수</span><span class="sxs-lookup"><span data-stu-id="48db9-117">Constant</span></span>  |<span data-ttu-id="48db9-118">값</span><span class="sxs-lookup"><span data-stu-id="48db9-118">Value</span></span>  |<span data-ttu-id="48db9-119">설명</span><span class="sxs-lookup"><span data-stu-id="48db9-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="48db9-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="48db9-120">0x8004101d</span></span> | <span data-ttu-id="48db9-121">[`BeginEnumeration`](beginenumeration.md) 함수에 대 한 호출이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="48db9-122">0</span><span class="sxs-lookup"><span data-stu-id="48db9-122">0</span></span> | <span data-ttu-id="48db9-123">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="48db9-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="48db9-124">0x40005</span></span> | <span data-ttu-id="48db9-125">열거형에 속성이 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="48db9-126">주의</span><span class="sxs-lookup"><span data-stu-id="48db9-126">Remarks</span></span>

<span data-ttu-id="48db9-127">이 함수는 [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="48db9-128">호출자는 [Beginmethodenumeration](beginmethodenumeration.md) 함수를 호출 하 여 열거형 시퀀스를 시작한 다음 함수가 `WBEM_S_NO_MORE_DATA`반환 될 때까지 [nextmethod] 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="48db9-129">필요에 따라 호출자는 [Endmethodenumeration](endmethodenumeration.md)을 호출 하 여 시퀀스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="48db9-130">호출자는 언제 든 지 [Endmethodenumeration](endmethodenumeration.md) 을 호출 하 여 열거형을 일찍 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48db9-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="48db9-131">예제</span><span class="sxs-lookup"><span data-stu-id="48db9-131">Example</span></span>

<span data-ttu-id="48db9-132">C++ 예제를 보려면 [IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48db9-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="48db9-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48db9-133">Requirements</span></span>  
 <span data-ttu-id="48db9-134">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48db9-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48db9-135">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="48db9-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="48db9-136">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="48db9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48db9-137">참조</span><span class="sxs-lookup"><span data-stu-id="48db9-137">See also</span></span>

- [<span data-ttu-id="48db9-138">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="48db9-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
