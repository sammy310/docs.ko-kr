---
title: SYMLINEDELTA 구조체
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609302"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="69621-102">SYMLINEDELTA 구조체</span><span class="sxs-lookup"><span data-stu-id="69621-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="69621-103">편집의 결과로 이동 된 메서드에 대 한 정보를 기호 처리기에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="69621-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69621-104">구문</span><span class="sxs-lookup"><span data-stu-id="69621-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="69621-105">멤버</span><span class="sxs-lookup"><span data-stu-id="69621-105">Members</span></span>  
  
|<span data-ttu-id="69621-106">멤버</span><span class="sxs-lookup"><span data-stu-id="69621-106">Member</span></span>|<span data-ttu-id="69621-107">설명</span><span class="sxs-lookup"><span data-stu-id="69621-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="69621-108">메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="69621-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="69621-109">메서드가 이동 된 줄의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="69621-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69621-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69621-110">Requirements</span></span>  
 <span data-ttu-id="69621-111">**헤더:** CorSym</span><span class="sxs-lookup"><span data-stu-id="69621-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69621-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69621-112">See also</span></span>

- [<span data-ttu-id="69621-113">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="69621-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
