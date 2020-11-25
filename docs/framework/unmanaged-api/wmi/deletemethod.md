---
title: DeleteMethod 함수 (관리 되지 않는 API 참조)
description: DeleteMethod 함수는 CIM 클래스 정의에서 지정 된 메서드를 삭제 합니다.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 8ca58ed3510360b20577890055e4284869d1bf94
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708103"
---
# <a name="deletemethod-function"></a><span data-ttu-id="b5298-103">DeleteMethod 함수</span><span class="sxs-lookup"><span data-stu-id="b5298-103">DeleteMethod function</span></span>

<span data-ttu-id="b5298-104">CIM 클래스 정의에서 지정 된 메서드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b5298-105">구문</span><span class="sxs-lookup"><span data-stu-id="b5298-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="b5298-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b5298-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b5298-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b5298-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="b5298-109">진행 클래스 테이블에서 제거할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="b5298-110">`wszName` 는 유효한에 대 한 포인터 여야 합니다 `LPCWSTR` .</span><span class="sxs-lookup"><span data-stu-id="b5298-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b5298-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="b5298-111">Return value</span></span>

<span data-ttu-id="b5298-112">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b5298-113">상수</span><span class="sxs-lookup"><span data-stu-id="b5298-113">Constant</span></span>  |<span data-ttu-id="b5298-114">값</span><span class="sxs-lookup"><span data-stu-id="b5298-114">Value</span></span>  |<span data-ttu-id="b5298-115">설명</span><span class="sxs-lookup"><span data-stu-id="b5298-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="b5298-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b5298-116">0x80041002</span></span> | <span data-ttu-id="b5298-117">지정 된 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b5298-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b5298-118">0x80041006</span></span> | <span data-ttu-id="b5298-119">메모리가 부족하여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b5298-120">0</span><span class="sxs-lookup"><span data-stu-id="b5298-120">0</span></span> | <span data-ttu-id="b5298-121">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b5298-122">설명</span><span class="sxs-lookup"><span data-stu-id="b5298-122">Remarks</span></span>

<span data-ttu-id="b5298-123">이 함수는 [IWbemClassObject::D eletemethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="b5298-124">CIM 인스턴스를 가리키는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포인터에는 메서드 삭제를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5298-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="b5298-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b5298-125">Requirements</span></span>  

 <span data-ttu-id="b5298-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5298-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5298-127">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="b5298-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b5298-128">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b5298-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5298-129">참조</span><span class="sxs-lookup"><span data-stu-id="b5298-129">See also</span></span>

- [<span data-ttu-id="b5298-130">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b5298-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
