---
description: '자세한 정보: SetNonAssemblyFlags 메서드'
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
ms.openlocfilehash: 9cf311ec8f04f97da03be626e20c1c07065eac38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662314"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="18603-103">SetNonAssemblyFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="18603-103">SetNonAssemblyFlags Method</span></span>

<span data-ttu-id="18603-104">어셈블리와 관련 없는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18603-104">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18603-105">구문</span><span class="sxs-lookup"><span data-stu-id="18603-105">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="18603-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18603-106">Parameters</span></span>  

 `afFlags`  
 <span data-ttu-id="18603-107">ALink 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="18603-107">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18603-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="18603-108">Return Value</span></span>  

 <span data-ttu-id="18603-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="18603-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18603-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18603-110">Requirements</span></span>  

 <span data-ttu-id="18603-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="18603-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18603-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18603-112">See also</span></span>

- [<span data-ttu-id="18603-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18603-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="18603-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18603-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="18603-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="18603-115">ALink API</span></span>](index.md)
