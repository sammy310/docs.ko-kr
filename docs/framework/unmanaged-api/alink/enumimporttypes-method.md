---
description: '다음에 대 한 자세한 정보: EnumImportTypes 메서드'
title: EnumImportTypes 메서드
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
ms.openlocfilehash: 39570740f3560f5bfef8ba80b95c0eb2aca41f59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638121"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="8dc16-103">EnumImportTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="8dc16-103">EnumImportTypes Method</span></span>

<span data-ttu-id="8dc16-104">각 범위에서 각 형식을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-104">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="8dc16-105">구문</span><span class="sxs-lookup"><span data-stu-id="8dc16-105">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="8dc16-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8dc16-106">Parameters</span></span>

`hEnum`\
<span data-ttu-id="8dc16-107">열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-107">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="8dc16-108">검색할 최대 형식 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-108">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="8dc16-109">는를 초과 하지 않는 형식 토큰을 받습니다 `dwMax` .</span><span class="sxs-lookup"><span data-stu-id="8dc16-109">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="8dc16-110">에서 형식의 실제 수를 수신 `aTypeDefs` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-110">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8dc16-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="8dc16-111">Return Value</span></span>

<span data-ttu-id="8dc16-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc16-112">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="8dc16-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8dc16-113">Requirements</span></span>

<span data-ttu-id="8dc16-114">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="8dc16-114">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="8dc16-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8dc16-115">See also</span></span>

- [<span data-ttu-id="8dc16-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8dc16-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8dc16-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8dc16-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8dc16-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="8dc16-118">ALink API</span></span>](index.md)
