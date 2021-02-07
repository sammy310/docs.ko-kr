---
description: '자세히 알아보기: ISymUnmanagedBinder3 인터페이스'
title: ISymUnmanagedBinder3 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: 6d2172fb119076cea6d0f912fb3f403d36856599
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689835"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="6b74c-103">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b74c-103">ISymUnmanagedBinder3 Interface</span></span>

<span data-ttu-id="6b74c-104">기호 바인더 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b74c-104">Extends the symbol binder interface.</span></span> <span data-ttu-id="6b74c-105">`QueryInterface`인터페이스를 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다 `ISymUnmanagedBinder` .</span><span class="sxs-lookup"><span data-stu-id="6b74c-105">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6b74c-106">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b74c-106">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b74c-107">메서드</span><span class="sxs-lookup"><span data-stu-id="6b74c-107">Methods</span></span>  
  
|<span data-ttu-id="6b74c-108">메서드</span><span class="sxs-lookup"><span data-stu-id="6b74c-108">Method</span></span>|<span data-ttu-id="6b74c-109">설명</span><span class="sxs-lookup"><span data-stu-id="6b74c-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b74c-110">GetReaderFromCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="6b74c-110">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="6b74c-111">사용자가 또는를 사용 하 여를 구현 하거나 제공 하 여 `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` 메모리에서 디버그 디렉터리 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b74c-111">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b74c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b74c-112">Requirements</span></span>  

 <span data-ttu-id="6b74c-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6b74c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b74c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b74c-114">See also</span></span>

- [<span data-ttu-id="6b74c-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b74c-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="6b74c-116">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b74c-116">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="6b74c-117">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b74c-117">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
