---
description: '자세히 알아보기: IAssemblyName:: GetVersion 메서드'
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
ms.openlocfilehash: 3339dda6a0b4f083655ece7bef86b080a8fcf5c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760721"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="bcc86-103">IAssemblyName::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="bcc86-103">IAssemblyName::GetVersion Method</span></span>

<span data-ttu-id="bcc86-104">이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리에 대 한 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bcc86-104">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc86-105">구문</span><span class="sxs-lookup"><span data-stu-id="bcc86-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcc86-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bcc86-106">Parameters</span></span>  

 `pdwVersionHi`  
 <span data-ttu-id="bcc86-107">제한이 버전의 상위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc86-107">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="bcc86-108">제한이 버전의 하위 32 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc86-108">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcc86-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bcc86-109">Requirements</span></span>  

 <span data-ttu-id="bcc86-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcc86-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcc86-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="bcc86-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bcc86-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcc86-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc86-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcc86-113">See also</span></span>

- [<span data-ttu-id="bcc86-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bcc86-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
