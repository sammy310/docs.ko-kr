---
title: EndMethodEnumeration 함수 (관리 되지 않는 API 참조)
description: EndMethodEnumeration 함수는 메서드 열거형 시퀀스를 종료 합니다.
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
ms.openlocfilehash: 174cf76d4b0ddf07e67e02bff20a983dca08819a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132015"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="08f19-103">EndMethodEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="08f19-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="08f19-104">[Beginmethodenumeration 함수](beginmethodenumeration.md)를 호출 하 여 시작 된 열거 시퀀스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="08f19-105">구문</span><span class="sxs-lookup"><span data-stu-id="08f19-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="08f19-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08f19-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="08f19-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="08f19-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="08f19-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="08f19-109">Return value</span></span>

<span data-ttu-id="08f19-110">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="08f19-111">상수</span><span class="sxs-lookup"><span data-stu-id="08f19-111">Constant</span></span>  |<span data-ttu-id="08f19-112">값</span><span class="sxs-lookup"><span data-stu-id="08f19-112">Value</span></span>  |<span data-ttu-id="08f19-113">설명</span><span class="sxs-lookup"><span data-stu-id="08f19-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="08f19-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="08f19-114">0x8004101d</span></span> | <span data-ttu-id="08f19-115">내부 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="08f19-116">0</span><span class="sxs-lookup"><span data-stu-id="08f19-116">0</span></span> | <span data-ttu-id="08f19-117">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="08f19-118">주의</span><span class="sxs-lookup"><span data-stu-id="08f19-118">Remarks</span></span>

<span data-ttu-id="08f19-119">이 함수는 [IWbemClassObject:: EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="08f19-120">호출자는 [Beginmethodenumeration 함수](beginmethodenumeration.md)를 사용 하 여 열거형 시퀀스를 시작한 다음 메서드가 `WBEM_S_NO_MORE_DATA`를 반환할 때까지 [nextmethod 함수](nextmethod.md )를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="08f19-121">호출자가 필요에 따라 `EndMethodEnumeration`를 호출 하 여 시퀀스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="08f19-122">호출자는 언제 든 지 `EndMethodEnumeration`를 호출 하 여 열거형을 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f19-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="08f19-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08f19-123">Requirements</span></span>  
 <span data-ttu-id="08f19-124">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08f19-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f19-125">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="08f19-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="08f19-126">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="08f19-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f19-127">참조</span><span class="sxs-lookup"><span data-stu-id="08f19-127">See also</span></span>

- [<span data-ttu-id="08f19-128">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="08f19-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
