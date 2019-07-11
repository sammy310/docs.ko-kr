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
ms.openlocfilehash: b0e6250987997b8d1c833b7b33a985900510fb03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742141"
---
# <a name="emitassembly-method"></a><span data-ttu-id="1edee-102">EmitAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="1edee-102">EmitAssembly Method</span></span>
<span data-ttu-id="1edee-103">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1edee-103">Creates the assembly.</span></span> <span data-ttu-id="1edee-104">다른 모든 파일은 어셈블리 파일을 제외 하 고 닫은 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1edee-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="1edee-105">바인딩되지 않은 모듈을 생성 하는 경우에이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1edee-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1edee-106">구문</span><span class="sxs-lookup"><span data-stu-id="1edee-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1edee-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1edee-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1edee-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1edee-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1edee-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="1edee-109">Return Value</span></span>  
 <span data-ttu-id="1edee-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1edee-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1edee-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1edee-111">Requirements</span></span>  
 <span data-ttu-id="1edee-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="1edee-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edee-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="1edee-113">See also</span></span>

- [<span data-ttu-id="1edee-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1edee-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1edee-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1edee-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1edee-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="1edee-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
