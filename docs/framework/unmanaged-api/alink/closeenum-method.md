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
ms.openlocfilehash: 59b1ec3f9ca382ef13680e3aad4d0c0c0e175f1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716969"
---
# <a name="closeenum-method"></a><span data-ttu-id="652e5-102">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="652e5-102">CloseEnum Method</span></span>

<span data-ttu-id="652e5-103">표시 된 열거형을 닫고 연결 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e5-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="652e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="652e5-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="652e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="652e5-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="652e5-106">닫을 열거형의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="652e5-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="652e5-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="652e5-107">Return Value</span></span>  

 <span data-ttu-id="652e5-108">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="652e5-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="652e5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="652e5-109">Requirements</span></span>  

 <span data-ttu-id="652e5-110">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="652e5-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="652e5-111">참조</span><span class="sxs-lookup"><span data-stu-id="652e5-111">See also</span></span>

- [<span data-ttu-id="652e5-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="652e5-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="652e5-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="652e5-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="652e5-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="652e5-114">ALink API</span></span>](index.md)
