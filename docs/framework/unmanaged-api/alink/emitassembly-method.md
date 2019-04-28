---
title: EmitAssembly 메서드
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf7b54ab7a2318e8194bf39dbe41b864633ddb43
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790067"
---
# <a name="emitassembly-method"></a><span data-ttu-id="ab432-102">EmitAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="ab432-102">EmitAssembly Method</span></span>
<span data-ttu-id="ab432-103">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab432-103">Creates the assembly.</span></span> <span data-ttu-id="ab432-104">다른 모든 파일은 어셈블리 파일을 제외 하 고 닫은 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab432-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="ab432-105">바인딩되지 않은 모듈을 생성 하는 경우에이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ab432-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab432-106">구문</span><span class="sxs-lookup"><span data-stu-id="ab432-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab432-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab432-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ab432-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab432-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab432-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ab432-109">Return Value</span></span>  
 <span data-ttu-id="ab432-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab432-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab432-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab432-111">Requirements</span></span>  
 <span data-ttu-id="ab432-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="ab432-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab432-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab432-113">See also</span></span>

- [<span data-ttu-id="ab432-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab432-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ab432-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab432-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ab432-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="ab432-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
