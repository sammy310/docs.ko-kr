---
title: EndMerge 메서드
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
ms.openlocfilehash: ed4ac7b12caa0dd78b79554258de62b8752553e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684930"
---
# <a name="endmerge-method"></a><span data-ttu-id="f9b0e-102">EndMerge 메서드</span><span class="sxs-lookup"><span data-stu-id="f9b0e-102">EndMerge Method</span></span>

<span data-ttu-id="f9b0e-103">모든 사용자 지정 특성이 내보내기 범위에 병합 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9b0e-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b0e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f9b0e-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9b0e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f9b0e-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f9b0e-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b0e-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9b0e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f9b0e-107">Return Value</span></span>  

 <span data-ttu-id="f9b0e-108">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b0e-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9b0e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9b0e-109">Requirements</span></span>  

 <span data-ttu-id="f9b0e-110">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="f9b0e-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b0e-111">참조</span><span class="sxs-lookup"><span data-stu-id="f9b0e-111">See also</span></span>

- [<span data-ttu-id="f9b0e-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9b0e-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f9b0e-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f9b0e-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f9b0e-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="f9b0e-114">ALink API</span></span>](index.md)
