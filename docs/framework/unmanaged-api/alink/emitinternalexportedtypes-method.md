---
description: '자세히 알아보기: EmitInternalExportedTypes 메서드'
title: EmitInternalExportedTypes 메서드
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
ms.openlocfilehash: 5d23c593988b31c077d3b65b11b73113e164ed74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638303"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="81ba6-103">EmitInternalExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="81ba6-103">EmitInternalExportedTypes Method</span></span>

<span data-ttu-id="81ba6-104">어셈블리에 추가 된 형식을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="81ba6-104">Emits types added to the assembly.</span></span> <span data-ttu-id="81ba6-105">알려진 내부 형식이 추가 된 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ba6-105">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81ba6-106">구문</span><span class="sxs-lookup"><span data-stu-id="81ba6-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="81ba6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="81ba6-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="81ba6-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81ba6-108">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81ba6-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="81ba6-109">Return Value</span></span>  

 <span data-ttu-id="81ba6-110">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ba6-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81ba6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81ba6-111">Requirements</span></span>  

 <span data-ttu-id="81ba6-112">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="81ba6-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ba6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81ba6-113">See also</span></span>

- [<span data-ttu-id="81ba6-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81ba6-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="81ba6-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81ba6-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="81ba6-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="81ba6-116">ALink API</span></span>](index.md)
