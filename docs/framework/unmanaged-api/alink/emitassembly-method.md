---
description: '자세히 알아보기: EmitAssembly 메서드'
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
ms.openlocfilehash: aada17d8df6435c5edfe6beb5db5ee13f887f253
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638342"
---
# <a name="emitassembly-method"></a><span data-ttu-id="6f941-103">EmitAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="6f941-103">EmitAssembly Method</span></span>

<span data-ttu-id="6f941-104">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f941-104">Creates the assembly.</span></span> <span data-ttu-id="6f941-105">어셈블리 파일을 제외 하 고 다른 모든 파일을 닫은 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f941-105">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="6f941-106">바인딩되지 않은 모듈을 생성할 때이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="6f941-106">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f941-107">구문</span><span class="sxs-lookup"><span data-stu-id="6f941-107">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f941-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f941-108">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="6f941-109">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6f941-109">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f941-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="6f941-110">Return Value</span></span>  

 <span data-ttu-id="6f941-111">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f941-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f941-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f941-112">Requirements</span></span>  

 <span data-ttu-id="6f941-113">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="6f941-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f941-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f941-114">See also</span></span>

- [<span data-ttu-id="6f941-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f941-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6f941-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f941-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6f941-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="6f941-117">ALink API</span></span>](index.md)
