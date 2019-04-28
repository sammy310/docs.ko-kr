---
title: CorSymVarFlag 열거형
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c797378f5e13f39c1c786237a3a7b9cf577fccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763652"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="e82ee-102">CorSymVarFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="e82ee-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="e82ee-103">컴파일러에서 생성 된 변수 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e82ee-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e82ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="e82ee-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="e82ee-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e82ee-105">Members</span></span>  
  
|<span data-ttu-id="e82ee-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e82ee-106">Member</span></span>|<span data-ttu-id="e82ee-107">설명</span><span class="sxs-lookup"><span data-stu-id="e82ee-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="e82ee-108">컴파일러에서 생성 되는 지정 된 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e82ee-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e82ee-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e82ee-109">Requirements</span></span>  
 <span data-ttu-id="e82ee-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e82ee-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82ee-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="e82ee-111">See also</span></span>

- [<span data-ttu-id="e82ee-112">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="e82ee-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
