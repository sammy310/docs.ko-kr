---
description: '자세히 알아보기: SYMLINEDELTA 구조체'
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
ms.openlocfilehash: ae00d2be9809b48180d2cd99d05e410624033419
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761449"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="4201f-103">SYMLINEDELTA 구조체</span><span class="sxs-lookup"><span data-stu-id="4201f-103">SYMLINEDELTA Structure</span></span>

<span data-ttu-id="4201f-104">편집의 결과로 이동 된 메서드에 대 한 정보를 기호 처리기에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-104">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4201f-105">구문</span><span class="sxs-lookup"><span data-stu-id="4201f-105">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="4201f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="4201f-106">Members</span></span>  
  
|<span data-ttu-id="4201f-107">멤버</span><span class="sxs-lookup"><span data-stu-id="4201f-107">Member</span></span>|<span data-ttu-id="4201f-108">설명</span><span class="sxs-lookup"><span data-stu-id="4201f-108">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="4201f-109">메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-109">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="4201f-110">메서드가 이동 된 줄의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-110">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4201f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4201f-111">Requirements</span></span>  

 <span data-ttu-id="4201f-112">**헤더:** CorSym</span><span class="sxs-lookup"><span data-stu-id="4201f-112">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4201f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4201f-113">See also</span></span>

- [<span data-ttu-id="4201f-114">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="4201f-114">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
