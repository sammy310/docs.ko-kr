---
title: InheritsFrom 함수 (관리 되지 않는 API 참조)
description: InheritsFrom 함수 클래스 또는 인스턴스를 특정 부모 클래스에서 파생 하는지 여부를 결정 합니다.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d2af1b41f47a3906c0e573c104847aa3ff36cf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040588"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="52078-103">InheritsFrom 함수</span><span class="sxs-lookup"><span data-stu-id="52078-103">InheritsFrom function</span></span>
<span data-ttu-id="52078-104">현재 클래스 또는 인스턴스가 지정된 부모 클래스에서 파생되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="52078-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="52078-105">구문</span><span class="sxs-lookup"><span data-stu-id="52078-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="52078-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52078-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="52078-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52078-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="52078-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="52078-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="52078-109">[in] 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52078-109">[in] The name of the class.</span></span> <span data-ttu-id="52078-110">`wszAncestor` 유효한 가리켜야 `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="52078-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="52078-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="52078-111">Return value</span></span>

<span data-ttu-id="52078-112">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="52078-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="52078-113">상수</span><span class="sxs-lookup"><span data-stu-id="52078-113">Constant</span></span>  |<span data-ttu-id="52078-114">값</span><span class="sxs-lookup"><span data-stu-id="52078-114">Value</span></span>  |<span data-ttu-id="52078-115">설명</span><span class="sxs-lookup"><span data-stu-id="52078-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="52078-116">0</span><span class="sxs-lookup"><span data-stu-id="52078-116">0</span></span> | <span data-ttu-id="52078-117">현재 개체에서 상속 `wszAncestor`합니다.</span><span class="sxs-lookup"><span data-stu-id="52078-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="52078-118">1</span><span class="sxs-lookup"><span data-stu-id="52078-118">1</span></span> | <span data-ttu-id="52078-119">현재 개체에서 상속 되지 않는 `wszAncestor`합니다.</span><span class="sxs-lookup"><span data-stu-id="52078-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="52078-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="52078-120">0x80041008</span></span> | <span data-ttu-id="52078-121">`wszAncestor`가 `null`인 경우</span><span class="sxs-lookup"><span data-stu-id="52078-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="52078-122">설명</span><span class="sxs-lookup"><span data-stu-id="52078-122">Remarks</span></span>

<span data-ttu-id="52078-123">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) 메서드.</span><span class="sxs-lookup"><span data-stu-id="52078-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="52078-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52078-124">Requirements</span></span>  
 <span data-ttu-id="52078-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="52078-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52078-126">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="52078-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="52078-127">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="52078-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52078-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="52078-128">See also</span></span>

- [<span data-ttu-id="52078-129">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="52078-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
