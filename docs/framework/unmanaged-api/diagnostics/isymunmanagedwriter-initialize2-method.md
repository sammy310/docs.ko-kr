---
title: ISymUnmanagedWriter::Initialize2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
ms.openlocfilehash: 869d7d36ac24bfeee5b2361dd569945ad77eaf7f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610069"
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="a48e3-102">ISymUnmanagedWriter::Initialize2 메서드</span><span class="sxs-lookup"><span data-stu-id="a48e3-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="a48e3-103">이 작성기를 연결할 메타 데이터 내보내기 인터페이스를 설정 하 고 디버깅 기호를 쓸 출력 파일 이름을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="a48e3-104">이 메서드를 사용 하 여 PDB (프로그램 데이터베이스) 파일의 최종 위치를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a48e3-105">구문</span><span class="sxs-lookup"><span data-stu-id="a48e3-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a48e3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a48e3-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="a48e3-107">진행 메타 데이터 내보내기 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="a48e3-108">진행 `WCHAR`디버깅 기호가 쓰여진 파일 이름이 포함 된에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="a48e3-109">파일 이름을 사용하지 않는 작성기에 대해 파일 이름이 지정되면 이 매개 변수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="a48e3-110">진행 지정 된 경우 기호 작성기는 <xref:System.Runtime.InteropServices.ComTypes.IStream> 매개 변수에 지정 된 파일이 아닌 지정 된으로 기호를 내보냅니다 `filename` .</span><span class="sxs-lookup"><span data-stu-id="a48e3-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="a48e3-111">`pIStream` 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="a48e3-112">[in] `true` 전체 다시 작성 인 경우 `false`증분 컴파일 인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="a48e3-113">진행 `WCHAR`PDB 파일의 마지막 위치에 대 한 경로 문자열인에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a48e3-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="a48e3-114">Return Value</span></span>  
 <span data-ttu-id="a48e3-115">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a48e3-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a48e3-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a48e3-116">Requirements</span></span>  
 <span data-ttu-id="a48e3-117">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a48e3-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48e3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a48e3-118">See also</span></span>

- [<span data-ttu-id="a48e3-119">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a48e3-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a48e3-120">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="a48e3-120">Initialize Method</span></span>](isymunmanagedwriter-initialize-method.md)
