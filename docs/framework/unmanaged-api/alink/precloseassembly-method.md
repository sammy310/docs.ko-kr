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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e1aeffbd5d5b22bea87dd7a49a3268822ce84d38
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481180"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="c3c2a-102">PreCloseAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="c3c2a-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="c3c2a-103">어셈블리 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c2a-103">Closes the assembly file.</span></span> <span data-ttu-id="c3c2a-104">다른 모든 파일을 닫은 후 어셈블리 파일을 닫기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c2a-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="c3c2a-105">바인딩되지 않은 모듈에 대 한이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c3c2a-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c2a-106">구문</span><span class="sxs-lookup"><span data-stu-id="c3c2a-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3c2a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3c2a-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c3c2a-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c2a-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3c2a-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3c2a-109">Return Value</span></span>  
 <span data-ttu-id="c3c2a-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c2a-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3c2a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3c2a-111">Requirements</span></span>  
 <span data-ttu-id="c3c2a-112">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c2a-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c2a-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3c2a-113">See also</span></span>
- [<span data-ttu-id="c3c2a-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3c2a-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c3c2a-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3c2a-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c3c2a-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="c3c2a-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
