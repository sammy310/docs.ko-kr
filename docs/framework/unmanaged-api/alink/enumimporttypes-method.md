---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cd154ac90418dd0f6f476151686ff670c01c98c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632241"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="34e69-102">EnumImportTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="34e69-102">EnumImportTypes Method</span></span>

<span data-ttu-id="34e69-103">각 범위에서 각 종류를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="34e69-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="34e69-104">구문</span><span class="sxs-lookup"><span data-stu-id="34e69-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="34e69-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="34e69-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="34e69-106">열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="34e69-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="34e69-107">최대 검색 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="34e69-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="34e69-108">넘지 형식 토큰을 받는 `dwMax`합니다.</span><span class="sxs-lookup"><span data-stu-id="34e69-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="34e69-109">실제 수를 입력 받는 `aTypeDefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="34e69-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="34e69-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="34e69-110">Return Value</span></span>

<span data-ttu-id="34e69-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="34e69-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="34e69-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="34e69-112">Requirements</span></span>

<span data-ttu-id="34e69-113">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="34e69-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="34e69-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="34e69-114">See also</span></span>

- [<span data-ttu-id="34e69-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34e69-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="34e69-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="34e69-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="34e69-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="34e69-117">ALink API</span></span>](index.md)
