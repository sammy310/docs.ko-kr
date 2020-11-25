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
ms.openlocfilehash: 31c0c5e23d1a985c2005693e25ca91379037482a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728682"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="e7730-102">PreCloseAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="e7730-102">PreCloseAssembly Method</span></span>

<span data-ttu-id="e7730-103">어셈블리 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e7730-103">Closes the assembly file.</span></span> <span data-ttu-id="e7730-104">다른 모든 파일을 닫은 후 어셈블리 파일을 닫기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7730-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="e7730-105">바인딩되지 않은 모듈에 대해이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e7730-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7730-106">구문</span><span class="sxs-lookup"><span data-stu-id="e7730-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7730-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e7730-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="e7730-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e7730-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7730-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="e7730-109">Return Value</span></span>  

 <span data-ttu-id="e7730-110">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7730-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7730-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7730-111">Requirements</span></span>  

 <span data-ttu-id="e7730-112">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7730-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7730-113">참조</span><span class="sxs-lookup"><span data-stu-id="e7730-113">See also</span></span>

- [<span data-ttu-id="e7730-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7730-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e7730-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7730-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e7730-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="e7730-116">ALink API</span></span>](index.md)
