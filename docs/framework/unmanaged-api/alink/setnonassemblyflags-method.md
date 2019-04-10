---
title: SetNonAssemblyFlags 메서드
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c7716db814e86258c4cb81047b39142f33798782
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143197"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="561c8-102">SetNonAssemblyFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="561c8-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="561c8-103">어셈블리와 관련 되지 않는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="561c8-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="561c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="561c8-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="561c8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="561c8-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="561c8-106">ALink 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="561c8-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="561c8-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="561c8-107">Return Value</span></span>  
 <span data-ttu-id="561c8-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="561c8-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="561c8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="561c8-109">Requirements</span></span>  
 <span data-ttu-id="561c8-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="561c8-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561c8-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="561c8-111">See also</span></span>

- [<span data-ttu-id="561c8-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="561c8-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="561c8-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="561c8-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="561c8-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="561c8-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
