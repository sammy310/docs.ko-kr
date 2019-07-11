---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15174480c4345f2514572701a5525f0f192ad120
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742094"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="608f9-102">EmitInternalExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="608f9-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="608f9-103">어셈블리에 추가 하는 형식을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="608f9-103">Emits types added to the assembly.</span></span> <span data-ttu-id="608f9-104">알려진 내부 형식이 추가 된 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="608f9-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="608f9-105">구문</span><span class="sxs-lookup"><span data-stu-id="608f9-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="608f9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="608f9-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="608f9-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="608f9-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="608f9-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="608f9-108">Return Value</span></span>  
 <span data-ttu-id="608f9-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="608f9-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="608f9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="608f9-110">Requirements</span></span>  
 <span data-ttu-id="608f9-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="608f9-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="608f9-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="608f9-112">See also</span></span>

- [<span data-ttu-id="608f9-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="608f9-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="608f9-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="608f9-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="608f9-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="608f9-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
