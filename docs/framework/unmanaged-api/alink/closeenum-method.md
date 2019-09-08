---
title: CloseEnum 메서드
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d9529022eb04c81152dced5c63f255c510851a0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777464"
---
# <a name="closeenum-method"></a><span data-ttu-id="855e7-102">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="855e7-102">CloseEnum Method</span></span>
<span data-ttu-id="855e7-103">표시 된 열거형을 닫고 연결 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="855e7-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="855e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="855e7-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="855e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="855e7-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="855e7-106">닫을 열거형의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="855e7-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="855e7-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="855e7-107">Return Value</span></span>  
 <span data-ttu-id="855e7-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="855e7-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="855e7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="855e7-109">Requirements</span></span>  
 <span data-ttu-id="855e7-110">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="855e7-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="855e7-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="855e7-111">See also</span></span>

- [<span data-ttu-id="855e7-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="855e7-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="855e7-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="855e7-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="855e7-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="855e7-114">ALink API</span></span>](index.md)
