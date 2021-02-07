---
description: '자세히 알아보기: ISymUnmanagedBinder2 인터페이스'
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
ms.openlocfilehash: 73847cdc9366ec18974fac261cbbad4d7dc6ccc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689887"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="a7c49-103">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7c49-103">ISymUnmanagedBinder2 Interface</span></span>

<span data-ttu-id="a7c49-104">비관리 코드에 대 한 기호 바인더를 나타내고 [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c49-104">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a7c49-105">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c49-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7c49-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a7c49-106">Methods</span></span>  
  
|<span data-ttu-id="a7c49-107">메서드</span><span class="sxs-lookup"><span data-stu-id="a7c49-107">Method</span></span>|<span data-ttu-id="a7c49-108">설명</span><span class="sxs-lookup"><span data-stu-id="a7c49-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7c49-109">GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="a7c49-109">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="a7c49-110">메타 데이터 인터페이스와 파일 이름이 지정 된 경우 모듈에 연결 된 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c49-110">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="a7c49-111">에서는 [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) 메서드 보다 더 광범위 한 검색을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c49-111">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7c49-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7c49-112">Requirements</span></span>  

 <span data-ttu-id="a7c49-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a7c49-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c49-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7c49-114">See also</span></span>

- [<span data-ttu-id="a7c49-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7c49-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="a7c49-116">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7c49-116">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="a7c49-117">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7c49-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
