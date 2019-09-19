---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: a74f71345a22f6d766c2d5966ca5d2cb33ab756e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053373"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="d4e1f-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="d4e1f-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="d4e1f-103">[IEnumRAWINPUTDEVIC: next](ienumrawinputdevic-next.md) 에 대 한 다음 `celt` 호출이 해당 요소를 반환 하지 않도록 열거자가 열거형의 다음 요소를 건너뛰도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4e1f-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e1f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d4e1f-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4e1f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4e1f-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="d4e1f-106">진행 건너뛸 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e1f-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d4e1f-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="d4e1f-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="d4e1f-108">HRESULT: 제공 된 요소의 수가 이면 S_OK이 `celt`고, 그렇지 않으면입니다. 그렇지 않으면 S_FALSE입니다.</span><span class="sxs-lookup"><span data-stu-id="d4e1f-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
