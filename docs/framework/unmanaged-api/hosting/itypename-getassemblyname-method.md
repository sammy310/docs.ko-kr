---
description: '자세히 알아보기: ITypeName:: GetAssemblyName 메서드'
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
ms.openlocfilehash: c2e84ec2fc7c6a300611643783d61b46c14997ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789348"
---
# <a name="itypenamegetassemblyname-method"></a><span data-ttu-id="44e75-103">ITypeName::GetAssemblyName 메서드</span><span class="sxs-lookup"><span data-stu-id="44e75-103">ITypeName::GetAssemblyName Method</span></span>

<span data-ttu-id="44e75-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="44e75-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e75-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="44e75-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyName (  
    [out, retval] BSTR* rgbszAssemblyNames  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="44e75-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44e75-106">Requirements</span></span>  

 <span data-ttu-id="44e75-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44e75-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e75-108">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="44e75-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44e75-109">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e75-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44e75-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e75-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e75-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44e75-111">See also</span></span>

- [<span data-ttu-id="44e75-112">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44e75-112">Hosting Interfaces</span></span>](hosting-interfaces.md)
