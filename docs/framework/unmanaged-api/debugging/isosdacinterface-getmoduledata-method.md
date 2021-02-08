---
description: '자세히 알아보기: ISOSDacInterface:: GetModuleData 메서드'
title: 'ISOSDacInterface:: GetModuleData 메서드'
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c01f55d55d5ee9082dee4b3adb3022bb17807aa2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790388"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="cfa28-103">ISOSDacInterface:: GetModuleData 메서드</span><span class="sxs-lookup"><span data-stu-id="cfa28-103">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="cfa28-104">지정 된 주소에서 로드 된 모듈에 해당 하는 데이터를 인출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa28-104">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="cfa28-105">구문</span><span class="sxs-lookup"><span data-stu-id="cfa28-105">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="cfa28-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cfa28-106">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="cfa28-107">진행 정보를 검색할 모듈의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa28-107">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="cfa28-108">제한이 로드 된 모듈의 정보를 저장할 [DacpModuleData 구조체](dacpmoduledata-structure.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="cfa28-108">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfa28-109">설명</span><span class="sxs-lookup"><span data-stu-id="cfa28-109">Remarks</span></span>

<span data-ttu-id="cfa28-110">제공 된 메서드는 인터페이스의 일부 이며 `ISOSDacInterface` 가상 메서드 테이블의 14 일 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfa28-110">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="cfa28-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cfa28-111">Requirements</span></span>

<span data-ttu-id="cfa28-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfa28-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="cfa28-113">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="cfa28-113">**Header:** None</span></span>  
<span data-ttu-id="cfa28-114">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="cfa28-114">**Library:** None</span></span>  
<span data-ttu-id="cfa28-115">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa28-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="cfa28-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfa28-116">See also</span></span>

- [<span data-ttu-id="cfa28-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="cfa28-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="cfa28-118">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cfa28-118">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
