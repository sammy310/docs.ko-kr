---
description: '다음에 대 한 자세한 정보: EnumCustomAttributes 메서드'
title: EnumCustomAttributes 메서드
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: d5b537462745914903f0cdb1e9f4436f2c27a68d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638136"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="5901c-103">EnumCustomAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="5901c-103">EnumCustomAttributes Method</span></span>

<span data-ttu-id="5901c-104">어셈블리 수준 사용자 지정 특성을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5901c-104">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5901c-105">구문</span><span class="sxs-lookup"><span data-stu-id="5901c-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5901c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5901c-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="5901c-107">열거자의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="5901c-107">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="5901c-108">열거할 특성의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5901c-108">Type of attributes to be enumerated.</span></span> <span data-ttu-id="5901c-109">`mdTokenNill`모든 특성에 대해를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5901c-109">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="5901c-110">사용자 지정 특성 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5901c-110">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5901c-111">배열의 크기를 지정 합니다 `rCustomValues` .</span><span class="sxs-lookup"><span data-stu-id="5901c-111">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="5901c-112">필요에 따라 토큰 값의 개수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5901c-112">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5901c-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="5901c-113">Return Value</span></span>  

 <span data-ttu-id="5901c-114">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5901c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5901c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5901c-115">Requirements</span></span>  

 <span data-ttu-id="5901c-116">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="5901c-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5901c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5901c-117">See also</span></span>

- [<span data-ttu-id="5901c-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5901c-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5901c-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5901c-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5901c-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="5901c-120">ALink API</span></span>](index.md)
