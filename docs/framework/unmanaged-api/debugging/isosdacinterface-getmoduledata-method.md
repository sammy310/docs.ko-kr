---
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
ms.openlocfilehash: 14e0eb812c84a0042150345d039451adf178caf1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396917"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="5602d-102">ISOSDacInterface:: GetModuleData 메서드</span><span class="sxs-lookup"><span data-stu-id="5602d-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="5602d-103">지정 된 주소에서 로드 된 모듈에 해당 하는 데이터를 인출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5602d-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5602d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5602d-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="5602d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5602d-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="5602d-106">진행 정보를 검색할 모듈의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5602d-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="5602d-107">제한이 로드 된 모듈의 정보를 저장할 [DacpModuleData 구조체](dacpmoduledata-structure.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="5602d-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="5602d-108">설명</span><span class="sxs-lookup"><span data-stu-id="5602d-108">Remarks</span></span>

<span data-ttu-id="5602d-109">제공 된 메서드는 인터페이스의 일부 이며 `ISOSDacInterface` 가상 메서드 테이블의 14 일 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5602d-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5602d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5602d-110">Requirements</span></span>

<span data-ttu-id="5602d-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5602d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5602d-112">**헤더:** 없음을</span><span class="sxs-lookup"><span data-stu-id="5602d-112">**Header:** None</span></span>  
<span data-ttu-id="5602d-113">**라이브러리:** 없음을</span><span class="sxs-lookup"><span data-stu-id="5602d-113">**Library:** None</span></span>  
<span data-ttu-id="5602d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5602d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5602d-115">참조</span><span class="sxs-lookup"><span data-stu-id="5602d-115">See also</span></span>

- [<span data-ttu-id="5602d-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="5602d-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="5602d-117">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5602d-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
