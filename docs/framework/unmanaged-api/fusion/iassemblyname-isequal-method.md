---
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
ms.openlocfilehash: 23bc251053dd27a7c5accb48ab4759ecdb79fe09
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134300"
---
# <a name="iassemblynameisequal-method"></a><span data-ttu-id="1b51d-102">IAssemblyName::IsEqual 메서드</span><span class="sxs-lookup"><span data-stu-id="1b51d-102">IAssemblyName::IsEqual Method</span></span>
<span data-ttu-id="1b51d-103">지정 된 [IAssemblyName](iassemblyname-interface.md) 개체가 지정 된 비교 플래그에 따라이 `IAssemblyName`와 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b51d-103">Determines whether a specified [IAssemblyName](iassemblyname-interface.md) object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b51d-104">구문</span><span class="sxs-lookup"><span data-stu-id="1b51d-104">Syntax</span></span>  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b51d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1b51d-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="1b51d-106">진행 이 `IAssemblyName`를 비교할 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1b51d-106">[in] The `IAssemblyName` object to which to compare this `IAssemblyName`.</span></span>  
  
 `dwCmpFlags`  
 <span data-ttu-id="1b51d-107">진행 비교에 영향을 주는 [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="1b51d-107">[in] A bitwise combination of [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) values that influence the comparison.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b51d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b51d-108">Requirements</span></span>  
 <span data-ttu-id="1b51d-109">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b51d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b51d-110">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="1b51d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1b51d-111">**.Net Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b51d-111">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b51d-112">참조</span><span class="sxs-lookup"><span data-stu-id="1b51d-112">See also</span></span>

- [<span data-ttu-id="1b51d-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b51d-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="1b51d-114">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="1b51d-114">Fusion Enumerations</span></span>](fusion-enumerations.md)
