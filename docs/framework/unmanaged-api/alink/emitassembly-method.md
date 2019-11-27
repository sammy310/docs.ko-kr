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
ms.openlocfilehash: 6bbe5db75ded15f32a6ff3564e1116d40a745a65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446528"
---
# <a name="emitassembly-method"></a><span data-ttu-id="88da3-102">EmitAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="88da3-102">EmitAssembly Method</span></span>
<span data-ttu-id="88da3-103">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88da3-103">Creates the assembly.</span></span> <span data-ttu-id="88da3-104">어셈블리 파일을 제외 하 고 다른 모든 파일을 닫은 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="88da3-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="88da3-105">바인딩되지 않은 모듈을 생성할 때이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="88da3-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88da3-106">구문</span><span class="sxs-lookup"><span data-stu-id="88da3-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="88da3-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88da3-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="88da3-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="88da3-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88da3-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="88da3-109">Return Value</span></span>  
 <span data-ttu-id="88da3-110">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88da3-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88da3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88da3-111">Requirements</span></span>  
 <span data-ttu-id="88da3-112">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="88da3-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88da3-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="88da3-113">See also</span></span>

- [<span data-ttu-id="88da3-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88da3-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="88da3-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88da3-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="88da3-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="88da3-116">ALink API</span></span>](index.md)
