---
title: ITypeName::GetNames 메서드
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
ms.openlocfilehash: 615dad9000b15ed13783ca41cc3c9fe2b563e15c
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842155"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="c9319-102">ITypeName::GetNames 메서드</span><span class="sxs-lookup"><span data-stu-id="c9319-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="c9319-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9319-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9319-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9319-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c9319-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9319-105">Requirements</span></span>  
 <span data-ttu-id="c9319-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9319-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9319-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c9319-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9319-108">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9319-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9319-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9319-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9319-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9319-110">See also</span></span>

- [<span data-ttu-id="c9319-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9319-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
