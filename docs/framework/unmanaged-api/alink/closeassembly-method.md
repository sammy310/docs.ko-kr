---
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
ms.openlocfilehash: 4e8aeef3520c4d5c9735b2c8975ac1e39470ba93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717023"
---
# <a name="closeassembly-method"></a><span data-ttu-id="c8a1c-102">CloseAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="c8a1c-102">CloseAssembly Method</span></span>

<span data-ttu-id="c8a1c-103">어셈블리 작업을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-103">Finalizes assembly operations.</span></span> <span data-ttu-id="c8a1c-104">새 어셈블리 또는 바인딩되지 않은 모듈을 시작 하기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8a1c-105">구문</span><span class="sxs-lookup"><span data-stu-id="c8a1c-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8a1c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8a1c-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="c8a1c-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8a1c-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c8a1c-108">Return Value</span></span>  

 <span data-ttu-id="c8a1c-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8a1c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8a1c-110">Requirements</span></span>  

 <span data-ttu-id="c8a1c-111">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8a1c-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a1c-112">참조</span><span class="sxs-lookup"><span data-stu-id="c8a1c-112">See also</span></span>

- [<span data-ttu-id="c8a1c-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8a1c-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c8a1c-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8a1c-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c8a1c-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="c8a1c-115">ALink API</span></span>](index.md)
