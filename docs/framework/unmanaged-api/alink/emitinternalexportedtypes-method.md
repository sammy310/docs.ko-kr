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
ms.openlocfilehash: c196bcc159b18b9dc04329d817ebe16e07bb8bb7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218253"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="76a79-102">EmitInternalExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="76a79-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="76a79-103">어셈블리에 추가 하는 형식을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="76a79-103">Emits types added to the assembly.</span></span> <span data-ttu-id="76a79-104">알려진 내부 형식이 추가 된 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a79-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a79-105">구문</span><span class="sxs-lookup"><span data-stu-id="76a79-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="76a79-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76a79-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="76a79-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="76a79-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76a79-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="76a79-108">Return Value</span></span>  
 <span data-ttu-id="76a79-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a79-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76a79-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76a79-110">Requirements</span></span>  
 <span data-ttu-id="76a79-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="76a79-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a79-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="76a79-112">See also</span></span>

- [<span data-ttu-id="76a79-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76a79-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="76a79-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76a79-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="76a79-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="76a79-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
