---
title: ICorPublishProcessEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 084af87acd73ef65739ba69ef2bd66d10d7c27c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790520"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="f45b9-102">ICorPublishProcessEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="f45b9-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="f45b9-103">현재 커서 위치에서 시작 하 여 컬렉션에서 지정 된 수의 프로세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f45b9-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f45b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="f45b9-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f45b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f45b9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f45b9-106">진행 검색할 프로세스의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f45b9-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="f45b9-107">제한이 각각 프로세스를 나타내는 검색 된 [ICorPublishProcess](icorpublishprocess-interface.md) 개체의 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f45b9-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f45b9-108">제한이 실제로 반환 된 프로세스 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f45b9-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="f45b9-109">`celt` 일 경우이 값은 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f45b9-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f45b9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f45b9-110">Requirements</span></span>  
 <span data-ttu-id="f45b9-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f45b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f45b9-112">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="f45b9-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f45b9-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f45b9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f45b9-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f45b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f45b9-115">참조</span><span class="sxs-lookup"><span data-stu-id="f45b9-115">See also</span></span>

- [<span data-ttu-id="f45b9-116">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f45b9-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
