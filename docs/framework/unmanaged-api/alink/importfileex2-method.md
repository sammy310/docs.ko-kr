---
title: ImportFileEx2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
ms.openlocfilehash: 59149e79e926a0b9a3e549e013bf178e54ddf6fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705178"
---
# <a name="importfileex2-method"></a><span data-ttu-id="e061b-102">ImportFileEx2 메서드</span><span class="sxs-lookup"><span data-stu-id="e061b-102">ImportFileEx2 Method</span></span>

<span data-ttu-id="e061b-103">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="e061b-104">이 메서드는 [Importfile 메서드와](importfile-method.md)유사 하지만, 가져오는 파일이 디스크에 존재 하지 않는 경우에도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e061b-105">구문</span><span class="sxs-lookup"><span data-stu-id="e061b-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e061b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e061b-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="e061b-107">가져올 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="e061b-108">대상 파일의 선택적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="e061b-109">선택적 가져오기 범위 [IMetaDataAssemblyImport interface](../metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="e061b-110">TRUE 이면 ImportTypes를 사용 합니다. 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="e061b-111">[Openscope 메서드에](../metadata/imetadatadispenser-openscope-method.md)따라 전달할 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="e061b-112">어셈블리나 파일의 고유 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="e061b-113">어셈블리 가져오기 범위 [IMetaDataAssemblyImport interface](../metadata/imetadataassemblyimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="e061b-114">파일이 어셈블리가 아닌 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="e061b-115">가져온 파일 및/또는 범위의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e061b-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="e061b-116">Return Value</span></span>  

 <span data-ttu-id="e061b-117">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e061b-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e061b-118">Requirements</span></span>  

 <span data-ttu-id="e061b-119">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e061b-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e061b-120">참조</span><span class="sxs-lookup"><span data-stu-id="e061b-120">See also</span></span>

- [<span data-ttu-id="e061b-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e061b-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e061b-122">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e061b-122">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e061b-123">ALink API</span><span class="sxs-lookup"><span data-stu-id="e061b-123">ALink API</span></span>](index.md)
