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
ms.openlocfilehash: d6c07a6679326548535985e4c938c3fddbb2a0cf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500215"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="cb4a0-102">SetNonAssemblyFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="cb4a0-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="cb4a0-103">어셈블리와 관련 되지 않는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4a0-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb4a0-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb4a0-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb4a0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb4a0-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="cb4a0-106">ALink 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4a0-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb4a0-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="cb4a0-107">Return Value</span></span>  
 <span data-ttu-id="cb4a0-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4a0-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb4a0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb4a0-109">Requirements</span></span>  
 <span data-ttu-id="cb4a0-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="cb4a0-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4a0-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="cb4a0-111">See also</span></span>
- [<span data-ttu-id="cb4a0-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb4a0-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="cb4a0-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb4a0-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="cb4a0-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="cb4a0-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
