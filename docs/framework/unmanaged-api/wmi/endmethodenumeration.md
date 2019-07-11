---
title: EndMethodEnumeration 함수 (관리 되지 않는 API 참조)
description: EndMethodEnumeration 함수 메서드 열거형 시퀀스를 종료합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f62ea692c055b0537394ad5e16501d4162faef12
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746836"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="0e36a-103">EndMethodEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="0e36a-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="0e36a-104">에 대 한 호출을 시작 하는 열거형 시퀀스를 종료 합니다 [BeginMethodEnumeration 함수](beginmethodenumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e36a-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="0e36a-105">구문</span><span class="sxs-lookup"><span data-stu-id="0e36a-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="0e36a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0e36a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0e36a-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e36a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0e36a-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="0e36a-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="0e36a-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="0e36a-109">Return value</span></span>

<span data-ttu-id="0e36a-110">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="0e36a-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0e36a-111">상수</span><span class="sxs-lookup"><span data-stu-id="0e36a-111">Constant</span></span>  |<span data-ttu-id="0e36a-112">값</span><span class="sxs-lookup"><span data-stu-id="0e36a-112">Value</span></span>  |<span data-ttu-id="0e36a-113">설명</span><span class="sxs-lookup"><span data-stu-id="0e36a-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="0e36a-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="0e36a-114">0x8004101d</span></span> | <span data-ttu-id="0e36a-115">내부 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e36a-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0e36a-116">0</span><span class="sxs-lookup"><span data-stu-id="0e36a-116">0</span></span> | <span data-ttu-id="0e36a-117">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e36a-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0e36a-118">설명</span><span class="sxs-lookup"><span data-stu-id="0e36a-118">Remarks</span></span>

<span data-ttu-id="0e36a-119">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) 메서드.</span><span class="sxs-lookup"><span data-stu-id="0e36a-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="0e36a-120">호출자에 게 사용 하 여 열거형 시퀀스를 시작 [BeginMethodEnumeration 함수](beginmethodenumeration.md)를 호출 하는 [NextMethod 함수](nextmethod.md )메서드가 반환 될 때까지 `WBEM_S_NO_MORE_DATA`입니다.</span><span class="sxs-lookup"><span data-stu-id="0e36a-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="0e36a-121">호출자가 호출 하 여 시퀀스를 필요에 따라 완료 `EndMethodEnumeration`합니다.</span><span class="sxs-lookup"><span data-stu-id="0e36a-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="0e36a-122">호출자에 게 해지할 수 있습니다 열거형 초기 호출 하 여 `EndMethodEnumeration` 언제 든 지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e36a-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e36a-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0e36a-123">Requirements</span></span>  
 <span data-ttu-id="0e36a-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0e36a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e36a-125">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0e36a-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0e36a-126">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0e36a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e36a-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e36a-127">See also</span></span>

- [<span data-ttu-id="0e36a-128">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="0e36a-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
