---
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
ms.openlocfilehash: 0c8d91c11205e06857b4a6e7edfedcd087270d00
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396938"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="e3d25-102">ISOSDacInterface:: GetMethodDescPtrFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="e3d25-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="e3d25-103">지정 된 기본 명령 주소를 포함 하는 메서드에 해당 하는 MethodDesc의 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3d25-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e3d25-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3d25-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="e3d25-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3d25-105">Parameters</span></span>

`ip`\
<span data-ttu-id="e3d25-106">진행 런타임에 메서드 내의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e3d25-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="e3d25-107">제한이 `MethodDesc`특정 메서드에 대 한의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e3d25-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3d25-108">설명</span><span class="sxs-lookup"><span data-stu-id="e3d25-108">Remarks</span></span>

<span data-ttu-id="e3d25-109">제공 된 메서드는 [ `ISOSDacInterface` 인터페이스](isosdacinterface-interface.md) 의 일부 이며 가상 메서드 테이블의 2 번째 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3d25-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3d25-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3d25-110">Requirements</span></span>

<span data-ttu-id="e3d25-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3d25-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e3d25-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="e3d25-112">**Header:** None</span></span>  
<span data-ttu-id="e3d25-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="e3d25-113">**Library:** None</span></span>  
<span data-ttu-id="e3d25-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e3d25-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e3d25-115">참조</span><span class="sxs-lookup"><span data-stu-id="e3d25-115">See also</span></span>

- [<span data-ttu-id="e3d25-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="e3d25-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="e3d25-117">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3d25-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
