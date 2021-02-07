---
description: '자세히 알아보기: PreCloseAssembly 메서드'
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
ms.openlocfilehash: 088a5bba654b3442da64672991d76537e9b4722c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662522"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="f5eb2-103">PreCloseAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="f5eb2-103">PreCloseAssembly Method</span></span>

<span data-ttu-id="f5eb2-104">어셈블리 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f5eb2-104">Closes the assembly file.</span></span> <span data-ttu-id="f5eb2-105">다른 모든 파일을 닫은 후 어셈블리 파일을 닫기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5eb2-105">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="f5eb2-106">바인딩되지 않은 모듈에 대해이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f5eb2-106">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5eb2-107">구문</span><span class="sxs-lookup"><span data-stu-id="f5eb2-107">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5eb2-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f5eb2-108">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f5eb2-109">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f5eb2-109">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5eb2-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="f5eb2-110">Return Value</span></span>  

 <span data-ttu-id="f5eb2-111">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5eb2-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5eb2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5eb2-112">Requirements</span></span>  

 <span data-ttu-id="f5eb2-113">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5eb2-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5eb2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5eb2-114">See also</span></span>

- [<span data-ttu-id="f5eb2-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5eb2-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f5eb2-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5eb2-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f5eb2-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="f5eb2-117">ALink API</span></span>](index.md)
