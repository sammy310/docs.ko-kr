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
ms.openlocfilehash: 2dcb363a2a84b3c2e0438e45663b96d9a0f83f61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445545"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="af7a7-102">SetNonAssemblyFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="af7a7-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="af7a7-103">어셈블리와 관련 없는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af7a7-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af7a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="af7a7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="af7a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af7a7-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="af7a7-106">ALink 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="af7a7-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af7a7-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="af7a7-107">Return Value</span></span>  
 <span data-ttu-id="af7a7-108">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af7a7-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af7a7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af7a7-109">Requirements</span></span>  
 <span data-ttu-id="af7a7-110">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="af7a7-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7a7-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="af7a7-111">See also</span></span>

- [<span data-ttu-id="af7a7-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af7a7-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="af7a7-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af7a7-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="af7a7-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="af7a7-114">ALink API</span></span>](index.md)
