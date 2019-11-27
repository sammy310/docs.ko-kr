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
ms.openlocfilehash: d4b7064b0339825c29e4001bc35c4a604098468a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446504"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="a1782-102">EmitInternalExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="a1782-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="a1782-103">어셈블리에 추가 된 형식을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1782-103">Emits types added to the assembly.</span></span> <span data-ttu-id="a1782-104">알려진 내부 형식이 추가 된 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1782-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1782-105">구문</span><span class="sxs-lookup"><span data-stu-id="a1782-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1782-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1782-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a1782-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a1782-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1782-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="a1782-108">Return Value</span></span>  
 <span data-ttu-id="a1782-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1782-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1782-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1782-110">Requirements</span></span>  
 <span data-ttu-id="a1782-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="a1782-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1782-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1782-112">See also</span></span>

- [<span data-ttu-id="a1782-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1782-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a1782-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1782-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a1782-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="a1782-115">ALink API</span></span>](index.md)
