---
title: IAssemblyName::GetVersion 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
ms.openlocfilehash: c0a43dc1640bdaa0ae104832eb4d1f8eb15b0392
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134328"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="76926-102">IAssemblyName::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="76926-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="76926-103">이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리에 대 한 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76926-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76926-104">구문</span><span class="sxs-lookup"><span data-stu-id="76926-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76926-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76926-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="76926-106">제한이 버전의 상위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="76926-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="76926-107">제한이 버전의 하위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="76926-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76926-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76926-108">Requirements</span></span>  
 <span data-ttu-id="76926-109">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76926-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76926-110">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="76926-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="76926-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76926-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76926-112">참조</span><span class="sxs-lookup"><span data-stu-id="76926-112">See also</span></span>

- [<span data-ttu-id="76926-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76926-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
