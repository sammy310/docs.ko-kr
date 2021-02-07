---
description: '자세히 알아보기: IAssemblyName:: IsEqual 메서드'
title: IAssemblyName::IsEqual 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
ms.openlocfilehash: f1bb0e26a217354e904ff79b397771d727a7a661
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760691"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="48ea2-103">IAssemblyName::IsEqual 메서드</span><span class="sxs-lookup"><span data-stu-id="48ea2-103">IAssemblyName::IsEqual Method</span></span>

<span data-ttu-id="48ea2-104">지정 된 [](iassemblyname-interface.md) `IAssemblyName` 비교 플래그에 따라 지정 된 IAssemblyName 개체가이와 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="48ea2-104">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ea2-105">구문</span><span class="sxs-lookup"><span data-stu-id="48ea2-105">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48ea2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48ea2-106">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="48ea2-107">진행 `IAssemblyName` 이와 비교할 개체 `IAssemblyName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="48ea2-107">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="48ea2-108">진행 비교에 영향을 주는 [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="48ea2-108">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48ea2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48ea2-109">Requirements</span></span>  

 <span data-ttu-id="48ea2-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48ea2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48ea2-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="48ea2-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="48ea2-112">**.Net Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48ea2-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ea2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48ea2-113">See also</span></span>

- [<span data-ttu-id="48ea2-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48ea2-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="48ea2-115">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="48ea2-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
