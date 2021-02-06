---
description: '자세한 정보: CloseEnum 메서드'
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
ms.openlocfilehash: 700c54de5af2e5c0be6940d4045019092655d46f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638381"
---
# <a name="closeenum-method"></a><span data-ttu-id="5402a-103">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="5402a-103">CloseEnum Method</span></span>

<span data-ttu-id="5402a-104">표시 된 열거형을 닫고 연결 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5402a-104">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5402a-105">구문</span><span class="sxs-lookup"><span data-stu-id="5402a-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5402a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5402a-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="5402a-107">닫을 열거형의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="5402a-107">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5402a-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="5402a-108">Return Value</span></span>  

 <span data-ttu-id="5402a-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5402a-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5402a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5402a-110">Requirements</span></span>  

 <span data-ttu-id="5402a-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="5402a-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5402a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5402a-112">See also</span></span>

- [<span data-ttu-id="5402a-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5402a-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5402a-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5402a-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5402a-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="5402a-115">ALink API</span></span>](index.md)
