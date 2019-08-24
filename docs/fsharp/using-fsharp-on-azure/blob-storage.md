---
title: F#을 사용하여 Azure Blob 스토리지 시작
description: Azure Blob storage를 사용 하 여 클라우드에 구조화 되지 않은 데이터를 저장 합니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: c8b42339ff1d76f262e956b5e34cc598e0fc855d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630515"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="889cc-103">F #을 사용 하 여 Azure Blob storage 시작\#</span><span class="sxs-lookup"><span data-stu-id="889cc-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="889cc-104">Azure Blob Storage는 클라우드에서 구조화되지 않은 데이터를 개체/Blob으로 저장하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="889cc-105">Blob Storage는 문서, 미디어 파일 또는 애플리케이션 설치 프로그램과 같은 모든 종류의 텍스트 또는 이진 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="889cc-106">Blob 스토리지를 개체 스토리지라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="889cc-107">이 문서에서는 Blob storage를 사용 하 여 일반적인 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="889cc-108">샘플은 .NET 용 Azure Storage F# 클라이언트 라이브러리를 사용 하 여 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="889cc-109">여기에서 설명 하는 태스크에는 blob을 업로드, 나열, 다운로드 및 삭제 하는 방법이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="889cc-110">Blob 저장소에 대 한 개념적 개요는 [blob 저장소에 대 한 .net 가이드](/azure/storage/storage-dotnet-how-to-use-blobs)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="889cc-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="889cc-111">전제 조건</span><span class="sxs-lookup"><span data-stu-id="889cc-111">Prerequisites</span></span>

<span data-ttu-id="889cc-112">이 가이드를 사용 하려면 먼저 [Azure storage 계정을 만들어야](/azure/storage/storage-create-storage-account)합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="889cc-113">이 계정에 대 한 저장소 액세스 키도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="889cc-114">F# 스크립트 만들기 및 대화형 시작 F#</span><span class="sxs-lookup"><span data-stu-id="889cc-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="889cc-115">이 문서의 샘플은 F# 응용 프로그램 또는 F# 스크립트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="889cc-116">F# 스크립트를 만들려면 `.fsx` F# 개발 환경에서 `blobs.fsx`확장명을 사용 하 여 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="889cc-117">그런 다음 [Paket](https://fsprojects.github.io/Paket/) 또는 `WindowsAzure.Storage` [NuGet](https://www.nuget.org/) 과 같은 [패키지 관리자](package-management.md) 를 사용 하 여 지시문을 `Microsoft.WindowsAzure.ConfigurationManager` `#r` 사용 하 여 `WindowsAzure.Storage.dll` 및 `Microsoft.WindowsAzure.Configuration.dll` 패키지를 설치 하 고 스크립트에 및를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="889cc-118">네임 스페이스 선언 추가</span><span class="sxs-lookup"><span data-stu-id="889cc-118">Add namespace declarations</span></span>

<span data-ttu-id="889cc-119">파일의 맨 `open` 위에 다음 문을 추가 합니다. `blobs.fsx`</span><span class="sxs-lookup"><span data-stu-id="889cc-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="889cc-120">연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="889cc-120">Get your connection string</span></span>

<span data-ttu-id="889cc-121">이 자습서에서는 Azure Storage 연결 문자열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="889cc-122">연결 문자열에 대 한 자세한 내용은 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="889cc-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="889cc-123">자습서의 경우 다음과 같이 스크립트에 연결 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="889cc-124">그러나 실제 프로젝트에는이 방법이 **권장 되지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="889cc-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="889cc-125">스토리지 계정 키는 스토리지 계정의 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="889cc-126">항상 스토리지 계정 키를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="889cc-127">다른 사용자에 게 배포 하거나 하드 코딩 하거나 다른 사용자가 액세스할 수 있는 일반 텍스트 파일로 저장 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="889cc-128">손상 된 것으로 생각 되는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="889cc-129">실제 응용 프로그램의 경우 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="889cc-130">구성 파일에서 연결 문자열을 가져오려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="889cc-131">Azure Configuration Manager 사용은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="889cc-132">.NET Framework의 `ConfigurationManager` 형식과 같은 API를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="889cc-133">연결 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="889cc-133">Parse the connection string</span></span>

<span data-ttu-id="889cc-134">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="889cc-135">그러면이 반환 `CloudStorageAccount`됩니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="889cc-136">로컬 더미 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="889cc-136">Create some local dummy data</span></span>

<span data-ttu-id="889cc-137">시작 하기 전에 스크립트의 디렉터리에 더미 로컬 데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="889cc-138">나중에이 데이터를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="889cc-139">Blob service 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="889cc-139">Create the Blob service client</span></span>

<span data-ttu-id="889cc-140">형식을 `CloudBlobClient` 사용 하 여 blob 저장소에 저장 된 컨테이너 및 blob을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="889cc-141">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="889cc-142">이제 데이터를 읽고 Blob 저장소에 데이터를 쓰는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="889cc-143">컨테이너 만들기</span><span class="sxs-lookup"><span data-stu-id="889cc-143">Create a container</span></span>

<span data-ttu-id="889cc-144">이 예제에서는 컨테이너가 아직 없는 경우 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="889cc-145">기본적으로 새 컨테이너는 전용입니다. 즉,이 컨테이너에서 blob을 다운로드 하려면 저장소 액세스 키를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="889cc-146">컨테이너 내의 파일을 모든 사용자가 사용할 수 있게 하려는 경우 다음 코드를 사용 하 여 컨테이너를 공용으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="889cc-147">인터넷 상의 누구 든 지 공용 컨테이너의 blob을 볼 수 있지만 적절 한 계정 액세스 키 또는 공유 액세스 서명이 있는 경우에만 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="889cc-148">컨테이너에 blob 업로드</span><span class="sxs-lookup"><span data-stu-id="889cc-148">Upload a blob into a container</span></span>

<span data-ttu-id="889cc-149">Azure Blob Storage는 블록 blob 및 페이지 blob을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="889cc-150">대부분의 경우 블록 blob은 사용 하기에 권장 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="889cc-151">블록 blob에 파일을 업로드 하려면 컨테이너 참조를 가져온 다음이 참조를 사용 하 여 블록 blob 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="889cc-152">Blob 참조가 있으면 메서드를 `UploadFromFile` 호출 하 여 데이터 스트림을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="889cc-153">이 작업은 blob이 없는 경우 새로 만들고, blob이 있는 경우 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="889cc-154">컨테이너의 blob 나열</span><span class="sxs-lookup"><span data-stu-id="889cc-154">List the blobs in a container</span></span>

<span data-ttu-id="889cc-155">컨테이너의 blob을 나열 하려면 먼저 컨테이너 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="889cc-156">그런 다음 컨테이너의 `ListBlobs` 메서드를 사용 하 여 컨테이너 내의 blob 및/또는 디렉터리를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="889cc-157">반환 `IListBlobItem`된에 대 한 다양 한 속성 및 메서드 집합에 액세스 하려면이 `CloudBlockBlob`를, `CloudPageBlob`또는 `CloudBlobDirectory` 개체로 캐스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="889cc-158">형식을 알 수 없는 경우 형식 검사를 사용 하 여 캐스팅할 형식을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="889cc-159">다음 코드에서는 `mydata` 컨테이너에 있는 각 항목의 URI를 검색 하 고 출력 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="889cc-160">이름에 경로 정보를 사용 하 여 blob의 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="889cc-161">이렇게 하면 기존 파일 시스템과 같이 구성 하 고 트래버스할 수 있는 가상 디렉터리 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="889cc-162">디렉터리 구조는 가상 전용입니다. Blob 저장소에서 사용할 수 있는 리소스는 컨테이너 및 blob 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="889cc-163">그러나 저장소 클라이언트 라이브러리는 가상 디렉터리를 `CloudBlobDirectory` 참조 하는 개체를 제공 하 고 이러한 방식으로 구성 된 blob을 사용 하 여 작업 하는 프로세스를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="889cc-164">예를 들어 라는 `photos`컨테이너에 있는 다음 블록 blob 집합을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="889cc-165">*photo1.jpg*</span><span class="sxs-lookup"><span data-stu-id="889cc-165">*photo1.jpg*</span></span>\
<span data-ttu-id="889cc-166">*2015/architecture/description.txt*</span><span class="sxs-lookup"><span data-stu-id="889cc-166">*2015/architecture/description.txt*</span></span>\
<span data-ttu-id="889cc-167">*2015/architecture/photo3.jpg*</span><span class="sxs-lookup"><span data-stu-id="889cc-167">*2015/architecture/photo3.jpg*</span></span>\
<span data-ttu-id="889cc-168">*2015/architecture/photo4.jpg*</span><span class="sxs-lookup"><span data-stu-id="889cc-168">*2015/architecture/photo4.jpg*</span></span>\
<span data-ttu-id="889cc-169">*2016/architecture/photo5.jpg*</span><span class="sxs-lookup"><span data-stu-id="889cc-169">*2016/architecture/photo5.jpg*</span></span>\
<span data-ttu-id="889cc-170">*2016/architecture/photo6.jpg*</span><span class="sxs-lookup"><span data-stu-id="889cc-170">*2016/architecture/photo6.jpg*</span></span>\
<span data-ttu-id="889cc-171">*2016/architecture/description.txt*</span><span class="sxs-lookup"><span data-stu-id="889cc-171">*2016/architecture/description.txt*</span></span>\
<span data-ttu-id="889cc-172">*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="889cc-172">*2016/photo7.jpg*</span></span>\

<span data-ttu-id="889cc-173">위의 샘플과 같이 `ListBlobs` 컨테이너에서를 호출 하면 계층적 목록이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="889cc-174">컨테이너의 디렉터리와 `CloudBlobDirectory` blob `CloudBlockBlob` 을 각각 나타내는 및 개체가 둘 다 포함 된 경우 결과 출력은 다음과 유사 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="889cc-175">필요에 따라 `UseFlatBlobListing` `ListBlobs` 메서드의 매개 변수를로 `true`설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="889cc-176">이 경우 컨테이너의 모든 blob이 `CloudBlockBlob` 개체로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="889cc-177">플랫 목록을 반환 `ListBlobs` 하기 위해에 대 한 호출은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="889cc-178">컨테이너의 현재 내용에 따라 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-178">and, depending on the current contents of your container, the results look like this:</span></span>

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a><span data-ttu-id="889cc-179">Blob 다운로드</span><span class="sxs-lookup"><span data-stu-id="889cc-179">Download blobs</span></span>

<span data-ttu-id="889cc-180">Blob을 다운로드 하려면 먼저 blob 참조를 검색 한 다음 메서드를 `DownloadToStream` 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="889cc-181">다음 예제에서는 `DownloadToStream` 메서드를 사용 하 여 blob 콘텐츠를 스트림 개체로 전송 합니다. 그러면이 개체를 로컬 파일에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="889cc-182">메서드를 `DownloadToStream` 사용 하 여 blob 콘텐츠를 텍스트 문자열로 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="889cc-183">Blob 삭제</span><span class="sxs-lookup"><span data-stu-id="889cc-183">Delete blobs</span></span>

<span data-ttu-id="889cc-184">Blob을 삭제 하려면 먼저 blob 참조를 가져온 다음 메서드를 `Delete` 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="889cc-185">비동기적으로 페이지의 blob 나열</span><span class="sxs-lookup"><span data-stu-id="889cc-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="889cc-186">많은 수의 blob을 나열 하거나 한 목록 작업에서 반환 하는 결과 수를 제어 하려는 경우 결과 페이지에 blob을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="889cc-187">이 예제에서는 많은 결과 집합을 반환 하기 위해 대기 하는 동안 실행이 차단 되지 않도록 페이지의 결과를 비동기적으로 반환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="889cc-188">이 예제에서는 플랫 blob 목록을 보여 주지만 `useFlatBlobListing` `ListBlobsSegmentedAsync` 메서드의 매개 변수를로 `false`설정 하 여 계층적 목록을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="889cc-189">이 샘플에서는 `async` 블록을 사용 하 여 비동기 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="889cc-190">키워드 ``let!`` 는 나열 작업이 완료 될 때까지 샘플 메서드의 실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="889cc-191">이제 다음과 같이이 비동기 루틴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="889cc-192">먼저이 자습서의 앞부분에서 만든 로컬 파일을 사용 하 여 더미 데이터를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="889cc-193">이제 루틴을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-193">Now, call the routine.</span></span> <span data-ttu-id="889cc-194">를 사용 `Async.RunSynchronously` 하 여 비동기 작업을 강제로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="889cc-195">추가 blob에 쓰기</span><span class="sxs-lookup"><span data-stu-id="889cc-195">Writing to an append blob</span></span>

<span data-ttu-id="889cc-196">추가 blob은 로깅과 같은 추가 작업에 최적화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="889cc-197">블록 blob과 마찬가지로 추가 blob은 블록으로 구성 되지만 추가 blob에 새 블록을 추가 하는 경우 항상 blob의 끝에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="889cc-198">추가 blob에서 기존 블록을 업데이트 하거나 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="889cc-199">추가 blob에 대 한 블록 Id는 블록 blob에 대 한 블록 Id로 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="889cc-200">추가 blob의 각 블록은 최대 4mb까지 다양 한 크기를 가질 수 있으며, 추가 blob은 최대 5만 블록을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="889cc-201">따라서 추가 blob의 최대 크기는 195 GB (4mb X 5만 블록) 보다 약간 더 됩니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="889cc-202">다음 예에서는 새 추가 blob을 만들고 일부 데이터를 추가 하 여 간단한 로깅 작업을 시뮬레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="889cc-203">3 가지 유형의 blob 간의 차이점에 대 한 자세한 내용은 [블록 blob, 페이지 blob 및 추가 Blob 이해](https://msdn.microsoft.com/library/azure/ee691964.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="889cc-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="889cc-204">동시 액세스</span><span class="sxs-lookup"><span data-stu-id="889cc-204">Concurrent access</span></span>

<span data-ttu-id="889cc-205">여러 클라이언트나 여러 프로세스 인스턴스에서 blob에 대 한 동시 액세스를 지원 하려면 **etag** 또는 **임대**를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="889cc-206">**Etag** -blob 또는 컨테이너가 다른 프로세스에 의해 수정 되었는지 감지 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="889cc-207">**임대** -일정 시간 동안 blob에 대 한 배타적, 갱신 가능, 쓰기 또는 삭제 권한을 얻는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="889cc-208">자세한 내용은 [Microsoft Azure Storage에서 동시성 관리](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="889cc-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="889cc-209">컨테이너 이름 지정</span><span class="sxs-lookup"><span data-stu-id="889cc-209">Naming containers</span></span>

<span data-ttu-id="889cc-210">Azure Storage의 모든 Blob은 컨테이너에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="889cc-211">컨테이너는 blob 이름의 일부를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-211">The container forms part of the blob name.</span></span> <span data-ttu-id="889cc-212">예를 들어 `mydata` 는 다음 샘플 blob uri에 있는 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="889cc-213">컨테이너 이름은 다음과 같은 명명 규칙을 준수 하는 유효한 DNS 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="889cc-214">컨테이너 이름은 문자 또는 숫자로 시작 해야 하며 문자, 숫자 및 대시 (-) 문자만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="889cc-215">모든 대시 (-) 문자는 바로 앞과 뒤에 문자 또는 숫자가와 야 합니다. 컨테이너 이름에는 연속 대시를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="889cc-216">컨테이너 이름의 모든 문자는 소문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="889cc-217">컨테이너 이름은 3 자에서 63 자 사이 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="889cc-218">컨테이너의 이름은 항상 소문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="889cc-219">컨테이너 이름에 대문자를 포함 하거나 컨테이너 명명 규칙을 위반 하는 경우 400 오류 (잘못 된 요청)가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="889cc-220">Blob에 대 한 보안 관리</span><span class="sxs-lookup"><span data-stu-id="889cc-220">Managing security for blobs</span></span>

<span data-ttu-id="889cc-221">기본적으로 Azure Storage는 계정 액세스 키를 소유 하는 계정 소유자에 대 한 액세스를 제한 하 여 데이터 보안을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="889cc-222">스토리지 계정의 Blob 데이터를 공유해야 할 경우 계정 액세스 키의 보안을 손상시키지 않고 공유하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="889cc-223">또한 blob 데이터를 암호화 하 여 네트워크를 통해 안전 하 게 전송 하 고 Azure Storage 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="889cc-224">Blob 데이터에 대 한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="889cc-224">Controlling access to blob data</span></span>

<span data-ttu-id="889cc-225">기본적으로 스토리지 계정의 Blob 데이터는 스토리지 계정 소유자만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="889cc-226">Blob 저장소에 대 한 요청을 인증 하려면 기본적으로 계정 액세스 키가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="889cc-227">그러나 특정 blob 데이터를 다른 사용자가 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="889cc-228">Blob 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="889cc-228">Encrypting blob data</span></span>

<span data-ttu-id="889cc-229">Azure Storage은 클라이언트와 서버 모두에서 blob 데이터를 암호화 하는 것을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="889cc-230">다음 단계</span><span class="sxs-lookup"><span data-stu-id="889cc-230">Next steps</span></span>

<span data-ttu-id="889cc-231">이제 Blob storage의 기본 사항을 배웠으므로 다음 링크를 따라 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="889cc-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="889cc-232">Tools</span><span class="sxs-lookup"><span data-stu-id="889cc-232">Tools</span></span>

- <span data-ttu-id="889cc-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span><span class="sxs-lookup"><span data-stu-id="889cc-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span></span>\
<span data-ttu-id="889cc-234">Blob F# , 테이블 및 큐 Azure Storage 자산을 탐색 하 고이에 대 한 CRUD 작업을 쉽게 적용 하는 데 사용할 수 있는 형식 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="889cc-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span><span class="sxs-lookup"><span data-stu-id="889cc-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span></span>\
<span data-ttu-id="889cc-236">Microsoft Azure F# Table Storage 서비스를 사용 하는 API</span><span class="sxs-lookup"><span data-stu-id="889cc-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="889cc-237">[Microsoft Azure Storage 탐색기 (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="889cc-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span></span>\
<span data-ttu-id="889cc-238">Windows, OS X 및 Linux에서 Azure Storage 데이터로 시각적으로 작업할 수 있도록 해 주는 Microsoft의 독립 실행형 무료 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="889cc-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="889cc-239">Blob storage 참조</span><span class="sxs-lookup"><span data-stu-id="889cc-239">Blob storage reference</span></span>

- [<span data-ttu-id="889cc-240">.NET 용 Azure Storage Api</span><span class="sxs-lookup"><span data-stu-id="889cc-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="889cc-241">Azure Storage Services REST API 참조</span><span class="sxs-lookup"><span data-stu-id="889cc-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="889cc-242">관련 가이드</span><span class="sxs-lookup"><span data-stu-id="889cc-242">Related guides</span></span>

- [<span data-ttu-id="889cc-243">에서 Azure Blob Storage 시작C#</span><span class="sxs-lookup"><span data-stu-id="889cc-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="889cc-244">Windows에서 AzCopy 명령줄 유틸리티를 사용 하 여 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="889cc-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="889cc-245">Linux에서 AzCopy 명령줄 유틸리티를 사용 하 여 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="889cc-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="889cc-246">Azure Storage 연결 문자열 구성</span><span class="sxs-lookup"><span data-stu-id="889cc-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="889cc-247">Azure Storage 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="889cc-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="889cc-248">빠른 시작: .NET을 사용 하 여 개체 저장소에 blob 만들기</span><span class="sxs-lookup"><span data-stu-id="889cc-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
