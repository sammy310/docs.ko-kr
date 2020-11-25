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
ms.openlocfilehash: c5a43f6c277f582f9f14cefe5bfba6f5300c09d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727356"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="49b10-102">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49b10-102">ISymUnmanagedBinder2 Interface</span></span>

<span data-ttu-id="49b10-103">비관리 코드에 대 한 기호 바인더를 나타내고 [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="49b10-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="49b10-104">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49b10-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49b10-105">메서드</span><span class="sxs-lookup"><span data-stu-id="49b10-105">Methods</span></span>  
  
|<span data-ttu-id="49b10-106">메서드</span><span class="sxs-lookup"><span data-stu-id="49b10-106">Method</span></span>|<span data-ttu-id="49b10-107">설명</span><span class="sxs-lookup"><span data-stu-id="49b10-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="49b10-108">GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="49b10-108">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="49b10-109">메타 데이터 인터페이스와 파일 이름이 지정 된 경우 모듈에 연결 된 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="49b10-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="49b10-110">에서는 [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) 메서드 보다 더 광범위 한 검색을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49b10-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49b10-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49b10-111">Requirements</span></span>  

 <span data-ttu-id="49b10-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="49b10-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b10-113">참조</span><span class="sxs-lookup"><span data-stu-id="49b10-113">See also</span></span>

- [<span data-ttu-id="49b10-114">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49b10-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="49b10-115">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49b10-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="49b10-116">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49b10-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
