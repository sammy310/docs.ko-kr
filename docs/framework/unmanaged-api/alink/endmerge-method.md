---
description: '자세히 알아보기: EndMerge 메서드'
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
ms.openlocfilehash: aac23d6d87f3fe74c1094bdd4a7f9c9f7f3fa7cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638160"
---
# <a name="endmerge-method"></a><span data-ttu-id="ff274-103">EndMerge 메서드</span><span class="sxs-lookup"><span data-stu-id="ff274-103">EndMerge Method</span></span>

<span data-ttu-id="ff274-104">모든 사용자 지정 특성이 내보내기 범위에 병합 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff274-104">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff274-105">구문</span><span class="sxs-lookup"><span data-stu-id="ff274-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff274-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff274-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="ff274-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ff274-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff274-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="ff274-108">Return Value</span></span>  

 <span data-ttu-id="ff274-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff274-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff274-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff274-110">Requirements</span></span>  

 <span data-ttu-id="ff274-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="ff274-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff274-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff274-112">See also</span></span>

- [<span data-ttu-id="ff274-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff274-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ff274-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff274-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ff274-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="ff274-115">ALink API</span></span>](index.md)
