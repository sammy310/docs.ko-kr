---
title: ISymUnmanagedBinder2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38de9fa878db18222d2666ba86420ca856e4b121
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940038"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="2d9e5-102">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2d9e5-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="2d9e5-103">비관리 코드의 기호 바인더를 나타냅니다 하 고 확장 합니다 [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9e5-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d9e5-104">이 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안 위험이 초래 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d9e5-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d9e5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2d9e5-105">Methods</span></span>  
  
|<span data-ttu-id="2d9e5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2d9e5-106">Method</span></span>|<span data-ttu-id="2d9e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="2d9e5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d9e5-108">GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="2d9e5-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="2d9e5-109">지정 된 메타 데이터 인터페이스 및 파일 이름을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 모듈과 관련 디버깅 기호를 읽는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9e5-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="2d9e5-110">보다 더 광범위 한 검색을 제공 합니다 [isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="2d9e5-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d9e5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d9e5-111">Requirements</span></span>  
 <span data-ttu-id="2d9e5-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d9e5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9e5-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d9e5-113">See also</span></span>

- [<span data-ttu-id="2d9e5-114">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2d9e5-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="2d9e5-115">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2d9e5-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="2d9e5-116">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2d9e5-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
