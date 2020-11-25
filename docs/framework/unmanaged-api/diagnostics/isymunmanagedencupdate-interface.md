---
title: ISymUnmanagedENCUpdate 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: 5e3c2ecd1bdd5c1181223c7500eb7473e20fa5d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731347"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="d7562-102">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7562-102">ISymUnmanagedENCUpdate Interface</span></span>

<span data-ttu-id="d7562-103">편집 하며 계속 하기 기능을 위한 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7562-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7562-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d7562-104">Methods</span></span>  
  
|<span data-ttu-id="d7562-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d7562-105">Method</span></span>|<span data-ttu-id="d7562-106">설명</span><span class="sxs-lookup"><span data-stu-id="d7562-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7562-107">GetLocalVariableCount 메서드</span><span class="sxs-lookup"><span data-stu-id="d7562-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="d7562-108">지역 변수 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7562-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="d7562-109">GetLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="d7562-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="d7562-110">지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7562-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="d7562-111">InitializeForEnc 메서드</span><span class="sxs-lookup"><span data-stu-id="d7562-111">InitializeForEnc Method</span></span>](isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="d7562-112">[ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) 메서드를 처음으로 호출 하기 전에 메서드 경계를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7562-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="d7562-113">UpdateMethodLines 메서드</span><span class="sxs-lookup"><span data-stu-id="d7562-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="d7562-114">다시 컴파일되지 않았지만 해당 줄이 독립적으로 이동 된 메서드에 대 한 줄 정보를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7562-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="d7562-115">각 문에 대 한 델타를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7562-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="d7562-116">UpdateSymbolStore2 메서드</span><span class="sxs-lookup"><span data-stu-id="d7562-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="d7562-117">줄 정보가 요구 사항을 충족 하는 경우 컴파일러가 PDB (프로그램 데이터베이스) 스트림에서 수정 되지 않은 함수를 생략할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7562-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="d7562-118">올바른 줄 정보는 이전 PDB 줄 정보와 함수의 모든 줄에 대해 델타 하나를 사용 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7562-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7562-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7562-119">Requirements</span></span>  

 <span data-ttu-id="d7562-120">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d7562-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7562-121">참조</span><span class="sxs-lookup"><span data-stu-id="d7562-121">See also</span></span>

- [<span data-ttu-id="d7562-122">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7562-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
