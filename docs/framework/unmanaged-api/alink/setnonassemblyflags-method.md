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
ms.openlocfilehash: e8a22e958740b69ba0e09bf062bf4d86075c3ff1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777015"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="f1e5a-102">SetNonAssemblyFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="f1e5a-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="f1e5a-103">어셈블리와 관련 없는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1e5a-104">구문</span><span class="sxs-lookup"><span data-stu-id="f1e5a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1e5a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1e5a-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="f1e5a-106">ALink 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1e5a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f1e5a-107">Return Value</span></span>  
 <span data-ttu-id="f1e5a-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e5a-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1e5a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1e5a-109">Requirements</span></span>  
 <span data-ttu-id="f1e5a-110">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="f1e5a-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e5a-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1e5a-111">See also</span></span>

- [<span data-ttu-id="f1e5a-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1e5a-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f1e5a-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1e5a-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f1e5a-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="f1e5a-114">ALink API</span></span>](index.md)
