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
ms.openlocfilehash: 1986d5f91a3dcfa31a43f729ee1f50129e083f5f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501744"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="2cc7f-102">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cc7f-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="2cc7f-103">편집 하며 계속 하기 기능을 위한 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2cc7f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2cc7f-104">Methods</span></span>  
  
|<span data-ttu-id="2cc7f-105">방법</span><span class="sxs-lookup"><span data-stu-id="2cc7f-105">Method</span></span>|<span data-ttu-id="2cc7f-106">설명</span><span class="sxs-lookup"><span data-stu-id="2cc7f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cc7f-107">GetLocalVariableCount 메서드</span><span class="sxs-lookup"><span data-stu-id="2cc7f-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="2cc7f-108">지역 변수 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="2cc7f-109">GetLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="2cc7f-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="2cc7f-110">지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="2cc7f-111">InitializeForEnc 메서드</span><span class="sxs-lookup"><span data-stu-id="2cc7f-111">InitializeForEnc Method</span></span>](isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="2cc7f-112">[ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) 메서드를 처음으로 호출 하기 전에 메서드 경계를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="2cc7f-113">UpdateMethodLines 메서드</span><span class="sxs-lookup"><span data-stu-id="2cc7f-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="2cc7f-114">다시 컴파일되지 않았지만 해당 줄이 독립적으로 이동 된 메서드에 대 한 줄 정보를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="2cc7f-115">각 문에 대 한 델타를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="2cc7f-116">UpdateSymbolStore2 메서드</span><span class="sxs-lookup"><span data-stu-id="2cc7f-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="2cc7f-117">줄 정보가 요구 사항을 충족 하는 경우 컴파일러가 PDB (프로그램 데이터베이스) 스트림에서 수정 되지 않은 함수를 생략할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="2cc7f-118">올바른 줄 정보는 이전 PDB 줄 정보와 함수의 모든 줄에 대해 델타 하나를 사용 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2cc7f-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cc7f-119">Requirements</span></span>  
 <span data-ttu-id="2cc7f-120">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2cc7f-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc7f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cc7f-121">See also</span></span>

- [<span data-ttu-id="2cc7f-122">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cc7f-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
