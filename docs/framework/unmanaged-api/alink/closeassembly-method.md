---
description: '자세한 정보: CloseAssembly 메서드'
title: CloseAssembly 메서드
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
ms.openlocfilehash: 927a66f948f691c00a695c626d9c31950a722cb5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638394"
---
# <a name="closeassembly-method"></a><span data-ttu-id="280b3-103">CloseAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="280b3-103">CloseAssembly Method</span></span>

<span data-ttu-id="280b3-104">어셈블리 작업을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="280b3-104">Finalizes assembly operations.</span></span> <span data-ttu-id="280b3-105">새 어셈블리 또는 바인딩되지 않은 모듈을 시작 하기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="280b3-105">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="280b3-106">구문</span><span class="sxs-lookup"><span data-stu-id="280b3-106">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="280b3-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="280b3-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="280b3-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="280b3-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="280b3-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="280b3-109">Return Value</span></span>  

 <span data-ttu-id="280b3-110">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="280b3-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="280b3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="280b3-111">Requirements</span></span>  

 <span data-ttu-id="280b3-112">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="280b3-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="280b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="280b3-113">See also</span></span>

- [<span data-ttu-id="280b3-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="280b3-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="280b3-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="280b3-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="280b3-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="280b3-116">ALink API</span></span>](index.md)
