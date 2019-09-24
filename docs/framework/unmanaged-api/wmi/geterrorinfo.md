---
title: GetErrorInfo 함수 (관리 되지 않는 API 참조)
description: GetErrorInfo 함수는 이전 함수 호출에서 오류 정보를 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab801ec7899403f568d953535fcd430a862a2fd8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798586"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="7c9be-103">GetErrorInfo 함수</span><span class="sxs-lookup"><span data-stu-id="7c9be-103">GetErrorInfo function</span></span>
<span data-ttu-id="7c9be-104">이전 함수 호출에서 오류 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9be-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7c9be-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c9be-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="7c9be-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="7c9be-106">Return value</span></span>

<span data-ttu-id="7c9be-107">함수 호출이 성공하거나 `null`실패한 경우 [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) 개체에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7c9be-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7c9be-108">설명</span><span class="sxs-lookup"><span data-stu-id="7c9be-108">Remarks</span></span>

<span data-ttu-id="7c9be-109">이 함수는 [IComThreadingInfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7c9be-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c9be-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c9be-110">Requirements</span></span>  
 <span data-ttu-id="7c9be-111">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c9be-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c9be-112">**헤더:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="7c9be-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="7c9be-113">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7c9be-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c9be-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7c9be-114">See also</span></span>

- [<span data-ttu-id="7c9be-115">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="7c9be-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
