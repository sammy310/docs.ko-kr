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
ms.openlocfilehash: 6f37979c7a4873a7751db0296dc7d485c3444561
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715903"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="02a7a-102">IAssemblyName::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="02a7a-102">IAssemblyName::GetVersion Method</span></span>

<span data-ttu-id="02a7a-103">이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리에 대 한 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02a7a-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="02a7a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02a7a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02a7a-105">Parameters</span></span>  

 `pdwVersionHi`  
 <span data-ttu-id="02a7a-106">제한이 버전의 상위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="02a7a-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="02a7a-107">제한이 버전의 하위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="02a7a-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a7a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02a7a-108">Requirements</span></span>  

 <span data-ttu-id="02a7a-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02a7a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a7a-110">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="02a7a-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="02a7a-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a7a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a7a-112">참조</span><span class="sxs-lookup"><span data-stu-id="02a7a-112">See also</span></span>

- [<span data-ttu-id="02a7a-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02a7a-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
