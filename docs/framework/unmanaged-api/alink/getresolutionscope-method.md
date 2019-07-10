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
ms.openlocfilehash: c6c2e741df594e265fdef51a602a9a4927733b7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741869"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="1ca7c-102">GetResolutionScope 메서드</span><span class="sxs-lookup"><span data-stu-id="1ca7c-102">GetResolutionScope Method</span></span>
<span data-ttu-id="1ca7c-103">지정 된 형식의 범위를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ca7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ca7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ca7c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ca7c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1ca7c-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1ca7c-107">참조를 수행 해야 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="1ca7c-108">파일의 토큰 형식임을 사용 하 여 검색에서 일반적으로 정의 됩니다 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="1ca7c-109">어셈블리 또는 모듈 참조를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ca7c-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ca7c-110">Return Value</span></span>  
 <span data-ttu-id="1ca7c-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ca7c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ca7c-112">Requirements</span></span>  
 <span data-ttu-id="1ca7c-113">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca7c-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ca7c-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="1ca7c-114">See also</span></span>

- [<span data-ttu-id="1ca7c-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ca7c-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1ca7c-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ca7c-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1ca7c-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="1ca7c-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
