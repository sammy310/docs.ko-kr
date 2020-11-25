---
title: ITypeName::GetAssemblyName 메서드
ms.date: 03/30/2017
api_name:
- ITypeName.GetAssemblyName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetAssemblyName
helpviewer_keywords:
- ITypeName::GetAssemblyName method [.NET Framework hosting]
- GetAssemblyName method [.NET Framework hosting]
ms.assetid: 97801d99-f5f1-4a30-882f-959827093fac
topic_type:
- apiref
ms.openlocfilehash: 256c0ccf7a39992ebb14adfd820729f8351e1990
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725120"
---
# <a name="itypenamegetassemblyname-method"></a><span data-ttu-id="f58de-102">ITypeName::GetAssemblyName 메서드</span><span class="sxs-lookup"><span data-stu-id="f58de-102">ITypeName::GetAssemblyName Method</span></span>

<span data-ttu-id="f58de-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f58de-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f58de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f58de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyName (  
    [out, retval] BSTR* rgbszAssemblyNames  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f58de-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f58de-105">Requirements</span></span>  

 <span data-ttu-id="f58de-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f58de-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f58de-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f58de-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f58de-108">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f58de-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f58de-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f58de-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f58de-110">참조</span><span class="sxs-lookup"><span data-stu-id="f58de-110">See also</span></span>

- [<span data-ttu-id="f58de-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f58de-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
