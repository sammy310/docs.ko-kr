---
title: 엔드메소메이션 함수(관리되지 않는 API 참조)
description: EndMethodEnumeration 함수는 메서드 열거 순서를 종료합니다.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175007"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="5f50b-103">EndMethodEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="5f50b-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="5f50b-104">[BeginMethodEnumeration 함수에](beginmethodenumeration.md)대한 호출로 시작된 열거 시퀀스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5f50b-105">구문</span><span class="sxs-lookup"><span data-stu-id="5f50b-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="5f50b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5f50b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5f50b-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5f50b-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="5f50b-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="5f50b-109">Return value</span></span>

<span data-ttu-id="5f50b-110">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5f50b-111">지속적임</span><span class="sxs-lookup"><span data-stu-id="5f50b-111">Constant</span></span>  |<span data-ttu-id="5f50b-112">값</span><span class="sxs-lookup"><span data-stu-id="5f50b-112">Value</span></span>  |<span data-ttu-id="5f50b-113">Description</span><span class="sxs-lookup"><span data-stu-id="5f50b-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="5f50b-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="5f50b-114">0x8004101d</span></span> | <span data-ttu-id="5f50b-115">내부 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5f50b-116">0</span><span class="sxs-lookup"><span data-stu-id="5f50b-116">0</span></span> | <span data-ttu-id="5f50b-117">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5f50b-118">설명</span><span class="sxs-lookup"><span data-stu-id="5f50b-118">Remarks</span></span>

<span data-ttu-id="5f50b-119">이 함수는 [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="5f50b-120">호출자는 [BeginMethodEnumeration 함수를](beginmethodenumeration.md)사용하여 열거 시퀀스를 시작한 다음 메서드가 `WBEM_S_NO_MORE_DATA`반환될 때까지 [NextMethod 함수를](nextmethod.md )호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="5f50b-121">호출자는 선택적으로 를 호출하여 `EndMethodEnumeration`시퀀스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="5f50b-122">호출자는 언제든지 호출하여 `EndMethodEnumeration` 열거를 조기에 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f50b-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f50b-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f50b-123">Requirements</span></span>  
 <span data-ttu-id="5f50b-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f50b-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f50b-125">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5f50b-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5f50b-126">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5f50b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f50b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f50b-127">See also</span></span>

- [<span data-ttu-id="5f50b-128">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="5f50b-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
