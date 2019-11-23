---
title: PreCloseAssembly 메서드
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
ms.openlocfilehash: fcfd3e79bbb52837a333b5ffacf5c13ae60f2490
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445617"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="78d62-102">PreCloseAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="78d62-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="78d62-103">Closes the assembly file.</span><span class="sxs-lookup"><span data-stu-id="78d62-103">Closes the assembly file.</span></span> <span data-ttu-id="78d62-104">Call this method after closing all other files, but before closing the assembly file.</span><span class="sxs-lookup"><span data-stu-id="78d62-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="78d62-105">Do not call this method for unbound modules.</span><span class="sxs-lookup"><span data-stu-id="78d62-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d62-106">구문</span><span class="sxs-lookup"><span data-stu-id="78d62-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="78d62-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78d62-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="78d62-108">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="78d62-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78d62-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="78d62-109">Return Value</span></span>  
 <span data-ttu-id="78d62-110">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="78d62-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78d62-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78d62-111">Requirements</span></span>  
 <span data-ttu-id="78d62-112">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="78d62-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d62-113">참조</span><span class="sxs-lookup"><span data-stu-id="78d62-113">See also</span></span>

- [<span data-ttu-id="78d62-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78d62-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="78d62-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78d62-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="78d62-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="78d62-116">ALink API</span></span>](index.md)
