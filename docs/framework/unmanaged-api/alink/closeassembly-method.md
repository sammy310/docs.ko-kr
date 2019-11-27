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
ms.openlocfilehash: 70dca19075d8c896408ec78f89549b0c539280de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446571"
---
# <a name="closeassembly-method"></a><span data-ttu-id="b7db6-102">CloseAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="b7db6-102">CloseAssembly Method</span></span>
<span data-ttu-id="b7db6-103">어셈블리 작업을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7db6-103">Finalizes assembly operations.</span></span> <span data-ttu-id="b7db6-104">새 어셈블리 또는 바인딩되지 않은 모듈을 시작 하기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7db6-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7db6-105">구문</span><span class="sxs-lookup"><span data-stu-id="b7db6-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7db6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7db6-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b7db6-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b7db6-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7db6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b7db6-108">Return Value</span></span>  
 <span data-ttu-id="b7db6-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7db6-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7db6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7db6-110">Requirements</span></span>  
 <span data-ttu-id="b7db6-111">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7db6-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7db6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7db6-112">See also</span></span>

- [<span data-ttu-id="b7db6-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7db6-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b7db6-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7db6-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b7db6-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="b7db6-115">ALink API</span></span>](index.md)
