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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d98ebed2eb853d5dc8177b0b044bf654c3978494
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744352"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="553b8-102">SYMLINEDELTA 구조체</span><span class="sxs-lookup"><span data-stu-id="553b8-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="553b8-103">편집 결과로 이동 된 메서드에 대 한 기호 처리기에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="553b8-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="553b8-104">구문</span><span class="sxs-lookup"><span data-stu-id="553b8-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="553b8-105">멤버</span><span class="sxs-lookup"><span data-stu-id="553b8-105">Members</span></span>  
  
|<span data-ttu-id="553b8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="553b8-106">Member</span></span>|<span data-ttu-id="553b8-107">설명</span><span class="sxs-lookup"><span data-stu-id="553b8-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="553b8-108">메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="553b8-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="553b8-109">메서드가 이동 된 줄의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="553b8-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="553b8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="553b8-110">Requirements</span></span>  
 <span data-ttu-id="553b8-111">**헤더:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="553b8-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553b8-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="553b8-112">See also</span></span>

- [<span data-ttu-id="553b8-113">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="553b8-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
