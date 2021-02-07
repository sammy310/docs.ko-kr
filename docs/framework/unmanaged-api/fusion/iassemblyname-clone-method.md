---
description: '자세히 알아보기: IAssemblyName:: Clone 메서드'
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
ms.openlocfilehash: b1d8ba2aec73565e9f6acaa44a5ef3731baa3af9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760786"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="60217-103">IAssemblyName::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="60217-103">IAssemblyName::Clone Method</span></span>

<span data-ttu-id="60217-104">이 [IAssemblyName](iassemblyname-interface.md) 개체의 단순 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60217-104">Creates a shallow copy of this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60217-105">구문</span><span class="sxs-lookup"><span data-stu-id="60217-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60217-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="60217-106">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="60217-107">제한이 이 개체의 반환 된 복사본 `IAssemblyName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="60217-107">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60217-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60217-108">Requirements</span></span>  

 <span data-ttu-id="60217-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60217-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60217-110">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="60217-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="60217-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60217-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60217-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60217-112">See also</span></span>

- [<span data-ttu-id="60217-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60217-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
