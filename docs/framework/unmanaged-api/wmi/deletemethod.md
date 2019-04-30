---
title: DeleteMethod 함수 (관리 되지 않는 API 참조)
description: DeleteMethod 함수 CIM 클래스 정의에서 지정된 된 메서드를 삭제합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eb96a75686a14182b9526a0832223c2b9abfc34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040679"
---
# <a name="deletemethod-function"></a><span data-ttu-id="97d3c-103">DeleteMethod 함수</span><span class="sxs-lookup"><span data-stu-id="97d3c-103">DeleteMethod function</span></span>
<span data-ttu-id="97d3c-104">CIM 클래스 정의에서 지정된 된 메서드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3c-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="97d3c-105">구문</span><span class="sxs-lookup"><span data-stu-id="97d3c-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="97d3c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97d3c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="97d3c-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="97d3c-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="97d3c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="97d3c-109">[in] 클래스 테이블에서 제거할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="97d3c-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="97d3c-110">`wszName` 유효한 포인터 여야 합니다. `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="97d3c-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="97d3c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="97d3c-111">Return value</span></span>

<span data-ttu-id="97d3c-112">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="97d3c-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="97d3c-113">상수</span><span class="sxs-lookup"><span data-stu-id="97d3c-113">Constant</span></span>  |<span data-ttu-id="97d3c-114">값</span><span class="sxs-lookup"><span data-stu-id="97d3c-114">Value</span></span>  |<span data-ttu-id="97d3c-115">설명</span><span class="sxs-lookup"><span data-stu-id="97d3c-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="97d3c-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="97d3c-116">0x80041002</span></span> | <span data-ttu-id="97d3c-117">지정된 된 메서드가 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3c-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="97d3c-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="97d3c-118">0x80041006</span></span> | <span data-ttu-id="97d3c-119">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3c-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="97d3c-120">0</span><span class="sxs-lookup"><span data-stu-id="97d3c-120">0</span></span> | <span data-ttu-id="97d3c-121">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="97d3c-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="97d3c-122">설명</span><span class="sxs-lookup"><span data-stu-id="97d3c-122">Remarks</span></span>

<span data-ttu-id="97d3c-123">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) 메서드.</span><span class="sxs-lookup"><span data-stu-id="97d3c-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="97d3c-124">메서드 삭제에 대 한 지원 되지 않습니다 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM 인스턴스를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="97d3c-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="97d3c-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97d3c-125">Requirements</span></span>  
 <span data-ttu-id="97d3c-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="97d3c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97d3c-127">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="97d3c-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="97d3c-128">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="97d3c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97d3c-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="97d3c-129">See also</span></span>

- [<span data-ttu-id="97d3c-130">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="97d3c-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
