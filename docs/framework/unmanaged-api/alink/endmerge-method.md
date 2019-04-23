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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 020cc56126249b27a52387e6efa3aa10c83d9126
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226849"
---
# <a name="endmerge-method"></a><span data-ttu-id="52636-102">EndMerge 메서드</span><span class="sxs-lookup"><span data-stu-id="52636-102">EndMerge Method</span></span>
<span data-ttu-id="52636-103">내보내기 범위에 모든 사용자 지정 특성 집합이 병합 된 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52636-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52636-104">구문</span><span class="sxs-lookup"><span data-stu-id="52636-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="52636-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52636-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="52636-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="52636-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52636-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="52636-107">Return Value</span></span>  
 <span data-ttu-id="52636-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="52636-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52636-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52636-109">Requirements</span></span>  
 <span data-ttu-id="52636-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="52636-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52636-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="52636-111">See also</span></span>

- [<span data-ttu-id="52636-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52636-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="52636-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52636-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="52636-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="52636-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
