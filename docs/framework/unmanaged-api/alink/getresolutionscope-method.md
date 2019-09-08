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
ms.openlocfilehash: a2bfb43002b79fd3e499272b87756bdc3ab0b589
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787334"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="98e43-102">GetResolutionScope 메서드</span><span class="sxs-lookup"><span data-stu-id="98e43-102">GetResolutionScope Method</span></span>
<span data-ttu-id="98e43-103">지정 된 형식의 범위를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e43-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98e43-104">구문</span><span class="sxs-lookup"><span data-stu-id="98e43-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="98e43-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98e43-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="98e43-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="98e43-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="98e43-107">참조를 필요로 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="98e43-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="98e43-108">형식이 정의 된 파일의 토큰으로, 일반적으로 [Importfile 메서드](importfile-method.md)를 사용 하 여 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e43-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="98e43-109">어셈블리 또는 모듈 참조를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e43-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98e43-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="98e43-110">Return Value</span></span>  
 <span data-ttu-id="98e43-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e43-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98e43-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98e43-112">Requirements</span></span>  
 <span data-ttu-id="98e43-113">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="98e43-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e43-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="98e43-114">See also</span></span>

- [<span data-ttu-id="98e43-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98e43-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="98e43-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98e43-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="98e43-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="98e43-117">ALink API</span></span>](index.md)
