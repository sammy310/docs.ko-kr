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
ms.openlocfilehash: cacf7eab1e53f590ad46fd98ed2f5dcbd14cd30a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434412"
---
# <a name="endmerge-method"></a><span data-ttu-id="35780-102">EndMerge 메서드</span><span class="sxs-lookup"><span data-stu-id="35780-102">EndMerge Method</span></span>
<span data-ttu-id="35780-103">모든 사용자 지정 특성이 내보내기 범위에 병합 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="35780-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35780-104">구문</span><span class="sxs-lookup"><span data-stu-id="35780-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="35780-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35780-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="35780-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35780-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35780-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="35780-107">Return Value</span></span>  
 <span data-ttu-id="35780-108">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35780-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35780-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35780-109">Requirements</span></span>  
 <span data-ttu-id="35780-110">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="35780-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35780-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35780-111">See also</span></span>

- [<span data-ttu-id="35780-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35780-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="35780-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35780-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="35780-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="35780-114">ALink API</span></span>](index.md)
