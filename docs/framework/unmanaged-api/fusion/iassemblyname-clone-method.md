---
title: IAssemblyName::Clone 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type:
- apiref
ms.openlocfilehash: 1236a574a85c01e3e1be5df9644bd04bbf0753ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134416"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="d3446-102">IAssemblyName::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="d3446-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="d3446-103">이 [IAssemblyName](iassemblyname-interface.md) 개체의 단순 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3446-103">Creates a shallow copy of this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3446-104">구문</span><span class="sxs-lookup"><span data-stu-id="d3446-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3446-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3446-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="d3446-106">제한이 이 `IAssemblyName` 개체의 반환 된 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="d3446-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3446-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3446-107">Requirements</span></span>  
 <span data-ttu-id="d3446-108">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3446-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3446-109">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d3446-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d3446-110">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3446-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3446-111">참조</span><span class="sxs-lookup"><span data-stu-id="d3446-111">See also</span></span>

- [<span data-ttu-id="d3446-112">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3446-112">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
