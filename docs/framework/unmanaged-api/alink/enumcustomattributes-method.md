---
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
ms.openlocfilehash: 445c833d10631341ef7ad579eaff8ddd96be3428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684852"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="44567-102">EnumCustomAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="44567-102">EnumCustomAttributes Method</span></span>

<span data-ttu-id="44567-103">어셈블리 수준 사용자 지정 특성을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="44567-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44567-104">구문</span><span class="sxs-lookup"><span data-stu-id="44567-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="44567-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44567-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="44567-106">열거자의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="44567-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="44567-107">열거할 특성의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="44567-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="44567-108">`mdTokenNill`모든 특성에 대해를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44567-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="44567-109">사용자 지정 특성 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="44567-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="44567-110">배열의 크기를 지정 합니다 `rCustomValues` .</span><span class="sxs-lookup"><span data-stu-id="44567-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="44567-111">필요에 따라 토큰 값의 개수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="44567-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44567-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="44567-112">Return Value</span></span>  

 <span data-ttu-id="44567-113">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44567-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44567-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44567-114">Requirements</span></span>  

 <span data-ttu-id="44567-115">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="44567-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44567-116">참조</span><span class="sxs-lookup"><span data-stu-id="44567-116">See also</span></span>

- [<span data-ttu-id="44567-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44567-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="44567-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44567-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="44567-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="44567-119">ALink API</span></span>](index.md)
