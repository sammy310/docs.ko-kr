---
title: EndEnumeration 함수 (관리 되지 않는 API 참조)
description: EndEnumeration 함수는 열거형을 종료 합니다.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0065dcd25430e102b965d5598c7e9a04c7857eb3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798817"
---
# <a name="endenumeration-function"></a><span data-ttu-id="b2725-103">EndEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="b2725-103">EndEnumeration function</span></span>

<span data-ttu-id="b2725-104">[Beginenumeration 함수](beginenumeration.md)를 호출 하 여 시작 된 열거 시퀀스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b2725-105">구문</span><span class="sxs-lookup"><span data-stu-id="b2725-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="b2725-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2725-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="b2725-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="b2725-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="b2725-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="b2725-109">Return value</span></span>

<span data-ttu-id="b2725-110">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b2725-111">상수</span><span class="sxs-lookup"><span data-stu-id="b2725-111">Constant</span></span>  |<span data-ttu-id="b2725-112">값</span><span class="sxs-lookup"><span data-stu-id="b2725-112">Value</span></span>  |<span data-ttu-id="b2725-113">Description</span><span class="sxs-lookup"><span data-stu-id="b2725-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b2725-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b2725-114">0x80041001</span></span> | <span data-ttu-id="b2725-115">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b2725-116">0</span><span class="sxs-lookup"><span data-stu-id="b2725-116">0</span></span> | <span data-ttu-id="b2725-117">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b2725-118">설명</span><span class="sxs-lookup"><span data-stu-id="b2725-118">Remarks</span></span>

<span data-ttu-id="b2725-119">이 함수는 [IWbemClassObject:: EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="b2725-120">`EndEnumeration` 함수를 호출 하는 것은 필수는 아니지만 열거와 연결 된 리소스를 해제 하기 때문에이 함수를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="b2725-121">그러나 다음 열거를 시작 하거나 개체를 해제할 때 리소스가 자동으로 할당 취소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2725-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2725-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2725-122">Requirements</span></span>

<span data-ttu-id="b2725-123">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b2725-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b2725-124">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b2725-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b2725-125">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b2725-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b2725-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2725-126">See also</span></span>

- [<span data-ttu-id="b2725-127">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b2725-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
