---
title: GetResolutionScope 메서드
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfe06c1300a22757b363236454f4f494dab1978a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486799"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="fc6a8-102">GetResolutionScope 메서드</span><span class="sxs-lookup"><span data-stu-id="fc6a8-102">GetResolutionScope Method</span></span>
<span data-ttu-id="fc6a8-103">지정 된 형식의 범위를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fc6a8-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc6a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc6a8-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc6a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc6a8-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fc6a8-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fc6a8-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="fc6a8-107">참조를 수행 해야 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fc6a8-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="fc6a8-108">파일의 토큰 형식임을 사용 하 여 검색에서 일반적으로 정의 됩니다 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc6a8-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="fc6a8-109">어셈블리 또는 모듈 참조를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fc6a8-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc6a8-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="fc6a8-110">Return Value</span></span>  
 <span data-ttu-id="fc6a8-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc6a8-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc6a8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc6a8-112">Requirements</span></span>  
 <span data-ttu-id="fc6a8-113">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fc6a8-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6a8-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="fc6a8-114">See also</span></span>
- [<span data-ttu-id="fc6a8-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc6a8-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fc6a8-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc6a8-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fc6a8-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="fc6a8-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
