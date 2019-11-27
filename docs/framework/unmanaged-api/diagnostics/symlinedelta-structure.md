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
ms.openlocfilehash: a1e83e4b8cb6603029f3b42b1a3b9ba4810c9039
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438005"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="a6263-102">SYMLINEDELTA 구조체</span><span class="sxs-lookup"><span data-stu-id="a6263-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="a6263-103">편집의 결과로 이동 된 메서드에 대 한 정보를 기호 처리기에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6263-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6263-104">구문</span><span class="sxs-lookup"><span data-stu-id="a6263-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="a6263-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a6263-105">Members</span></span>  
  
|<span data-ttu-id="a6263-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a6263-106">Member</span></span>|<span data-ttu-id="a6263-107">설명</span><span class="sxs-lookup"><span data-stu-id="a6263-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="a6263-108">메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a6263-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="a6263-109">메서드가 이동 된 줄의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6263-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6263-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6263-110">Requirements</span></span>  
 <span data-ttu-id="a6263-111">**헤더:** CorSym</span><span class="sxs-lookup"><span data-stu-id="a6263-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6263-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6263-112">See also</span></span>

- [<span data-ttu-id="a6263-113">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="a6263-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
