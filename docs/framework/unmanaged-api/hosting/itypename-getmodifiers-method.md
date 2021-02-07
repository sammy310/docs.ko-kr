---
description: '자세히 알아보기: ITypeName:: GetModifiers 메서드'
title: ITypeName::GetModifiers 메서드
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: 3c44d569255656f95ccceec0462d09044b46679b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753720"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="a9c30-103">ITypeName::GetModifiers 메서드</span><span class="sxs-lookup"><span data-stu-id="a9c30-103">ITypeName::GetModifiers Method</span></span>

<span data-ttu-id="a9c30-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9c30-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c30-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9c30-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a9c30-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9c30-106">Requirements</span></span>  

 <span data-ttu-id="a9c30-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9c30-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9c30-108">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a9c30-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9c30-109">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9c30-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9c30-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9c30-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c30-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9c30-111">See also</span></span>

- [<span data-ttu-id="a9c30-112">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9c30-112">Hosting Interfaces</span></span>](hosting-interfaces.md)
