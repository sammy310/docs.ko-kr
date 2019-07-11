---
title: ISOSDacInterface::GetMethodDescPtrFromIP 메서드
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
ms.openlocfilehash: cd256250021436e611142de11c3625a21aeec814
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764748"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="2f595-102">ISOSDacInterface::GetMethodDescPtrFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="2f595-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="2f595-103">특정된 네이티브 명령 주소를 포함 하는 메서드를 해당 MethodDesc의 포인터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f595-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2f595-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f595-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="2f595-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f595-105">Parameters</span></span>

`ip`\
<span data-ttu-id="2f595-106">[in] 런타임 시 메서드 내에서 사용 되는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f595-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="2f595-107">[out] 주소는 `MethodDesc` 특정 메서드에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f595-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f595-108">설명</span><span class="sxs-lookup"><span data-stu-id="2f595-108">Remarks</span></span>

<span data-ttu-id="2f595-109">제공 된 메서드는의 일부를 [ `ISOSDacInterface` 인터페이스](isosdacinterface-interface.md) 가상 메서드 테이블의 21 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f595-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f595-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f595-110">Requirements</span></span>

<span data-ttu-id="2f595-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f595-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2f595-112">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="2f595-112">**Header:** None</span></span>  
<span data-ttu-id="2f595-113">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="2f595-113">**Library:** None</span></span>  
<span data-ttu-id="2f595-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2f595-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2f595-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f595-115">See also</span></span>

- [<span data-ttu-id="2f595-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="2f595-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="2f595-117">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f595-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
