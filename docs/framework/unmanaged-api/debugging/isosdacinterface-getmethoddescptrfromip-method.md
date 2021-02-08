---
description: '자세히 알아보기: ISOSDacInterface:: GetMethodDescPtrFromIP 메서드'
title: 'ISOSDacInterface:: GetMethodDescPtrFromIP 메서드'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 8d7c7071b7b3fc520faea71c8d7792317745cfde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790414"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="b7567-103">ISOSDacInterface:: GetMethodDescPtrFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="b7567-103">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="b7567-104">지정 된 기본 명령 주소를 포함 하는 메서드에 해당 하는 MethodDesc의 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7567-104">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b7567-105">구문</span><span class="sxs-lookup"><span data-stu-id="b7567-105">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="b7567-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7567-106">Parameters</span></span>

`ip`\
<span data-ttu-id="b7567-107">진행 런타임에 메서드 내의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b7567-107">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="b7567-108">제한이 `MethodDesc` 특정 메서드에 대 한의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b7567-108">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7567-109">설명</span><span class="sxs-lookup"><span data-stu-id="b7567-109">Remarks</span></span>

<span data-ttu-id="b7567-110">제공 된 메서드는 [ `ISOSDacInterface` 인터페이스](isosdacinterface-interface.md) 의 일부 이며 가상 메서드 테이블의 2 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7567-110">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7567-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7567-111">Requirements</span></span>

<span data-ttu-id="b7567-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7567-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b7567-113">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="b7567-113">**Header:** None</span></span>  
<span data-ttu-id="b7567-114">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="b7567-114">**Library:** None</span></span>  
<span data-ttu-id="b7567-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b7567-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b7567-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7567-116">See also</span></span>

- [<span data-ttu-id="b7567-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="b7567-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="b7567-118">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7567-118">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
