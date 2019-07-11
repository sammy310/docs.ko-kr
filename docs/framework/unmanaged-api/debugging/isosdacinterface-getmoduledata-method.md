---
title: ISOSDacInterface::GetModuleData 메서드
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
ms.openlocfilehash: 97b297def9fba329ff6d9573f7b2e7cc811273f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764713"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="9023a-102">ISOSDacInterface::GetModuleData 메서드</span><span class="sxs-lookup"><span data-stu-id="9023a-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="9023a-103">주어진된 주소에 로드 된 모듈에 해당 데이터를 인출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9023a-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9023a-104">구문</span><span class="sxs-lookup"><span data-stu-id="9023a-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="9023a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9023a-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="9023a-106">[in] 주소에 대 한 정보를 검색 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="9023a-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="9023a-107">[out] 합니다 [DacpModuleData 구조](dacpmoduledata-structure.md) 로드 된 모듈의 정보를 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="9023a-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="9023a-108">설명</span><span class="sxs-lookup"><span data-stu-id="9023a-108">Remarks</span></span>

<span data-ttu-id="9023a-109">제공 된 메서드는의 일부는 `ISOSDacInterface` 인터페이스 및 가상 메서드 테이블의 13 슬롯에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9023a-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9023a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9023a-110">Requirements</span></span>

<span data-ttu-id="9023a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9023a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9023a-112">**헤더:** 없음</span><span class="sxs-lookup"><span data-stu-id="9023a-112">**Header:** None</span></span>  
<span data-ttu-id="9023a-113">**라이브러리:** 없음</span><span class="sxs-lookup"><span data-stu-id="9023a-113">**Library:** None</span></span>  
<span data-ttu-id="9023a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9023a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9023a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9023a-115">See also</span></span>

- [<span data-ttu-id="9023a-116">디버깅</span><span class="sxs-lookup"><span data-stu-id="9023a-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="9023a-117">ISOSDacInterface 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9023a-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
