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
ms.openlocfilehash: 6318890dd6f0259d8d6a7675380684a129c14c8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684679"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="45e1a-102">GetResolutionScope 메서드</span><span class="sxs-lookup"><span data-stu-id="45e1a-102">GetResolutionScope Method</span></span>

<span data-ttu-id="45e1a-103">지정 된 형식의 범위를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="45e1a-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e1a-104">구문</span><span class="sxs-lookup"><span data-stu-id="45e1a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="45e1a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45e1a-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="45e1a-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="45e1a-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="45e1a-107">참조를 필요로 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="45e1a-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="45e1a-108">형식이 정의 된 파일의 토큰으로, 일반적으로 [Importfile 메서드](importfile-method.md)를 사용 하 여 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="45e1a-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="45e1a-109">어셈블리 또는 모듈 참조를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="45e1a-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45e1a-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="45e1a-110">Return Value</span></span>  

 <span data-ttu-id="45e1a-111">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="45e1a-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45e1a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45e1a-112">Requirements</span></span>  

 <span data-ttu-id="45e1a-113">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="45e1a-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e1a-114">참조</span><span class="sxs-lookup"><span data-stu-id="45e1a-114">See also</span></span>

- [<span data-ttu-id="45e1a-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45e1a-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="45e1a-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45e1a-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="45e1a-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="45e1a-117">ALink API</span></span>](index.md)
