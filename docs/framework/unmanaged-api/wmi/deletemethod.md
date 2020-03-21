---
title: 삭제 메서드 함수(관리되지 않는 API 참조)
description: DeleteMethod 함수는 CIM 클래스 정의에서 지정된 메서드를 삭제합니다.
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
ms.openlocfilehash: 4059555d74c0b0f151332ddcf9faedecf238e795
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174994"
---
# <a name="deletemethod-function"></a><span data-ttu-id="75b69-103">DeleteMethod 함수</span><span class="sxs-lookup"><span data-stu-id="75b69-103">DeleteMethod function</span></span>
<span data-ttu-id="75b69-104">CIM 클래스 정의에서 지정된 메서드를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="75b69-105">구문</span><span class="sxs-lookup"><span data-stu-id="75b69-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="75b69-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75b69-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="75b69-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="75b69-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="75b69-109">【인】 클래스 테이블에서 제거할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="75b69-110">`wszName`유효한 `LPCWSTR`에 대한 포인터여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="75b69-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="75b69-111">Return value</span></span>

<span data-ttu-id="75b69-112">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="75b69-113">지속적임</span><span class="sxs-lookup"><span data-stu-id="75b69-113">Constant</span></span>  |<span data-ttu-id="75b69-114">값</span><span class="sxs-lookup"><span data-stu-id="75b69-114">Value</span></span>  |<span data-ttu-id="75b69-115">Description</span><span class="sxs-lookup"><span data-stu-id="75b69-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="75b69-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="75b69-116">0x80041002</span></span> | <span data-ttu-id="75b69-117">지정된 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="75b69-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="75b69-118">0x80041006</span></span> | <span data-ttu-id="75b69-119">메모리가 부족하여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="75b69-120">0</span><span class="sxs-lookup"><span data-stu-id="75b69-120">0</span></span> | <span data-ttu-id="75b69-121">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="75b69-122">설명</span><span class="sxs-lookup"><span data-stu-id="75b69-122">Remarks</span></span>

<span data-ttu-id="75b69-123">이 함수는 [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="75b69-124">CIM 인스턴스를 가리키는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포인터에는 메서드 삭제가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75b69-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="75b69-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75b69-125">Requirements</span></span>  
 <span data-ttu-id="75b69-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75b69-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75b69-127">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="75b69-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="75b69-128">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="75b69-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b69-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75b69-129">See also</span></span>

- [<span data-ttu-id="75b69-130">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="75b69-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
