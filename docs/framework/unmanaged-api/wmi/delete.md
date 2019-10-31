---
title: Delete 함수 (관리 되지 않는 API 참조)
description: Delete 함수는 CIM 클래스 정의에서 지정 된 속성 및 모든 한정자를 삭제 합니다.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6b8f287be831702dd31a8335f9b2f6447bcee540
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127660"
---
# <a name="delete-function"></a><span data-ttu-id="b1c48-103">Delete 함수</span><span class="sxs-lookup"><span data-stu-id="b1c48-103">Delete function</span></span>

<span data-ttu-id="b1c48-104">CIM 클래스 정의에서 지정 된 속성 및 모든 한정자를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b1c48-105">구문</span><span class="sxs-lookup"><span data-stu-id="b1c48-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="b1c48-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1c48-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="b1c48-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="b1c48-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="b1c48-109">진행 삭제할 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="b1c48-110">`wszName`은 유효한 `LPCWSTR`에 대 한 포인터 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b1c48-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b1c48-111">Return value</span></span>

<span data-ttu-id="b1c48-112">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b1c48-113">상수</span><span class="sxs-lookup"><span data-stu-id="b1c48-113">Constant</span></span>  |<span data-ttu-id="b1c48-114">값</span><span class="sxs-lookup"><span data-stu-id="b1c48-114">Value</span></span>  |<span data-ttu-id="b1c48-115">설명</span><span class="sxs-lookup"><span data-stu-id="b1c48-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="b1c48-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b1c48-116">0x80041001</span></span> | <span data-ttu-id="b1c48-117">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="b1c48-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="b1c48-118">0x80041016</span></span> | <span data-ttu-id="b1c48-119">속성을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b1c48-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b1c48-120">0x80041008</span></span> | <span data-ttu-id="b1c48-121">`wszName`이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="b1c48-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b1c48-122">0x80041002</span></span> | <span data-ttu-id="b1c48-123">지정 된 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b1c48-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b1c48-124">0x80041006</span></span> | <span data-ttu-id="b1c48-125">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="b1c48-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="b1c48-126">0x8004101c</span></span> | <span data-ttu-id="b1c48-127">속성은 기본 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="b1c48-128">속성은 시스템 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b1c48-129">0</span><span class="sxs-lookup"><span data-stu-id="b1c48-129">0</span></span> | <span data-ttu-id="b1c48-130">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="b1c48-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="b1c48-131">0x80041030</span></span> | <span data-ttu-id="b1c48-132">함수가 현재 클래스의 재정의 기본값을 삭제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="b1c48-133">부모 클래스에서이 속성의 기본값이 다시 활성화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b1c48-134">주의</span><span class="sxs-lookup"><span data-stu-id="b1c48-134">Remarks</span></span>

<span data-ttu-id="b1c48-135">이 함수는 [IWbemClassObject::D e)](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b1c48-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1c48-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1c48-136">Requirements</span></span>

<span data-ttu-id="b1c48-137">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1c48-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b1c48-138">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="b1c48-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b1c48-139">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b1c48-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b1c48-140">참조</span><span class="sxs-lookup"><span data-stu-id="b1c48-140">See also</span></span>

- [<span data-ttu-id="b1c48-141">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b1c48-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
