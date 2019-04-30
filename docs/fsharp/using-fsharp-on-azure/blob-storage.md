---
title: 사용 하 여 Azure Blob storage 시작F#
description: Azure Blob storage 사용 하 여 클라우드에 구조화 되지 않은 데이터를 저장 합니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 62178edf22ad48d0388f34488b68d135068d50a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982516"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="eac22-103">F를 사용 하 여 Azure Blob storage 시작\#</span><span class="sxs-lookup"><span data-stu-id="eac22-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="eac22-104">Azure Blob Storage는 클라우드에서 구조화되지 않은 데이터를 개체/Blob으로 저장하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="eac22-105">Blob Storage는 문서, 미디어 파일, 애플리케이션 설치 관리자 등과 같은 모든 유형의 텍스트 또는 이진 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="eac22-106">Blob 스토리지를 개체 스토리지라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="eac22-107">이 문서에서는 Blob storage를 사용 하 여 일반적인 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="eac22-108">샘플은 사용 하 여 작성 되었습니다 F# .NET 용 Azure Storage 클라이언트 라이브러리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="eac22-109">대상 작업을 업로드, 나열, 다운로드 및 blob을 삭제 하는 방법을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="eac22-110">Blob 저장소의 개념적인 개요를 참조 하세요 [blob storage에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-blobs)합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eac22-111">전제 조건</span><span class="sxs-lookup"><span data-stu-id="eac22-111">Prerequisites</span></span>

<span data-ttu-id="eac22-112">이 가이드를 사용 하려면 먼저 [Azure storage 계정 만들기](/azure/storage/storage-create-storage-account)합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="eac22-113">이 계정에 대 한 저장소 액세스 키도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="eac22-114">만들기는 F# 스크립트 및 시작 F# 대화형</span><span class="sxs-lookup"><span data-stu-id="eac22-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="eac22-115">이 문서의 샘플에서 사용할 수는 F# 응용 프로그램 또는 F# 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="eac22-116">만들려는 F# 스크립트를 사용 하 여 파일을 만듭니다는 `.fsx` 예를 들어 확장 `blobs.fsx`에서 F# 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="eac22-117">다음을 사용 하 여는 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 설치 하는 `WindowsAzure.Storage` 및 `Microsoft.WindowsAzure.ConfigurationManager` 패키지와 참조 `WindowsAzure.Storage.dll` 및 `Microsoft.WindowsAzure.Configuration.dll` 사용 하 여 스크립트를 `#r` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="eac22-118">네임 스페이스 선언을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="eac22-118">Add namespace declarations</span></span>

<span data-ttu-id="eac22-119">다음을 추가 합니다 `open` 의 맨 위에 문을 `blobs.fsx` 파일:</span><span class="sxs-lookup"><span data-stu-id="eac22-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="eac22-120">연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="eac22-120">Get your connection string</span></span>

<span data-ttu-id="eac22-121">이 자습서는 Azure Storage 연결 문자열이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="eac22-122">연결 문자열에 대 한 자세한 내용은 참조 하세요. [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="eac22-123">자습서의 경우 다음과 같은 스크립트에서 연결 문자열을 입력:</span><span class="sxs-lookup"><span data-stu-id="eac22-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="eac22-124">그러나 이것이 **좋지** 실제 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="eac22-125">저장소 계정 키는 저장소 계정의 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="eac22-126">항상 저장소 계정 키를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="eac22-127">다른 사용자에 하드 코딩 하거나 다른 사용자에 게 액세스할 수 있는 일반 텍스트 파일을 저장 하 게 배포 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="eac22-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="eac22-128">손상 되었다고 생각 하는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="eac22-129">실제 응용 프로그램 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에서 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="eac22-130">구성 파일에서 연결 문자열을 가져올,이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="eac22-131">Azure 구성 관리자를 사용 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="eac22-132">.NET Framework의 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="eac22-133">연결 문자열을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="eac22-133">Parse the connection string</span></span>

<span data-ttu-id="eac22-134">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="eac22-135">반환 된 `CloudStorageAccount`합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="eac22-136">몇 가지 로컬 더미 데이터 만들기</span><span class="sxs-lookup"><span data-stu-id="eac22-136">Create some local dummy data</span></span>

<span data-ttu-id="eac22-137">시작 하기 전에 스크립트의 디렉터리에 더미 로컬 데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="eac22-138">나중에이 데이터를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="eac22-139">Blob service 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="eac22-139">Create the Blob service client</span></span>

<span data-ttu-id="eac22-140">`CloudBlobClient` 컨테이너 및 Blob storage에 저장 된 blob을 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="eac22-141">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="eac22-142">이제 데이터를 읽어 오고 Blob storage로 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="eac22-143">컨테이너 만들기</span><span class="sxs-lookup"><span data-stu-id="eac22-143">Create a container</span></span>

<span data-ttu-id="eac22-144">이 예제에는 아직 존재 하지 않는 경우 컨테이너를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="eac22-145">기본적으로 새 컨테이너는 private,이 컨테이너에서 blob을 다운로드 하려면 저장소 액세스 키를 지정 해야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="eac22-146">모든 사용자에 게 컨테이너 내의 파일을 사용할 수 있도록 하려는 경우에 다음 코드를 사용 하 여 공용 컨테이너를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="eac22-147">인터넷 상의 누구 든 지 공용 컨테이너의 blob를 볼 수 있지만 수정 하거나 적절 한 계정 액세스 키 또는 공유 액세스 서명이 있는 경우에 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="eac22-148">컨테이너에 blob 업로드</span><span class="sxs-lookup"><span data-stu-id="eac22-148">Upload a blob into a container</span></span>

<span data-ttu-id="eac22-149">Azure Blob Storage는 블록 blob 및 페이지 blob을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="eac22-150">대부분의 경우 블록 blob의는 권장 되는 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="eac22-151">파일에 블록 blob을 업로드 하려면 컨테이너 참조를 가져오고 사용 하 여 블록 blob 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="eac22-152">Blob 참조가 있으면 스트림을 업로드할 수 있습니다 모든 데이터를 호출 하 여는 `UploadFromFile` 메서드.</span><span class="sxs-lookup"><span data-stu-id="eac22-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="eac22-153">이 작업은 이전에 존재 하거나 없는 경우 덮어 쓸까요 하지 않은 경우 blob을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="eac22-154">컨테이너의 blob을 나열</span><span class="sxs-lookup"><span data-stu-id="eac22-154">List the blobs in a container</span></span>

<span data-ttu-id="eac22-155">컨테이너의 blob을 나열 하려면 먼저 컨테이너 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="eac22-156">컨테이너의 사용할 수 있습니다 `ListBlobs` blob 및/또는 그 디렉터리를 검색 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="eac22-157">속성 및 메서드 반환 된 다양 한 집합에 액세스 하려면 `IListBlobItem`를 캐스트 해야를 `CloudBlockBlob`를 `CloudPageBlob`, 또는 `CloudBlobDirectory` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="eac22-158">종류를 알 수 없는 경우 캐스트 확인할 형식 검사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="eac22-159">다음 코드에는 검색의 각 항목의 URI를 출력 하는 방법을 보여 줍니다.는 `mydata` 컨테이너:</span><span class="sxs-lookup"><span data-stu-id="eac22-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="eac22-160">이름에 대 한 경로 정보를 사용 하 여 이름을 blob 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="eac22-161">이 구성 하 고 기존 파일 시스템과 마찬가지로 트래버스할 수 있는 가상 디렉터리 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="eac22-162">디렉터리 구조는 가상만 해당-컨테이너 및 blob는 Blob storage에서 사용할 수 있는 리소스만 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="eac22-163">그러나 storage 클라이언트 라이브러리를 제공 된 `CloudBlobDirectory` 가상 디렉터리를 참조 하 여이 방식으로 구성 된 blob을 사용 하는 프로세스를 간소화 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="eac22-164">예를 들어, 다음 라는 컨테이너에 블록 blob 집합을 고려 `photos`:</span><span class="sxs-lookup"><span data-stu-id="eac22-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="eac22-165">*photo1.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="eac22-165">*photo1.jpg*\\</span></span>
<span data-ttu-id="eac22-166">*2015/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="eac22-166">*2015/architecture/description.txt*\\</span></span>
<span data-ttu-id="eac22-167">*2015/architecture/photo3.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="eac22-167">*2015/architecture/photo3.jpg*\\</span></span>
<span data-ttu-id="eac22-168">*2015/architecture/photo4.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="eac22-168">*2015/architecture/photo4.jpg*\\</span></span>
<span data-ttu-id="eac22-169">*2016/architecture/photo5.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="eac22-169">*2016/architecture/photo5.jpg*\\</span></span>
<span data-ttu-id="eac22-170">*2016/architecture/photo6.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="eac22-170">*2016/architecture/photo6.jpg*\\</span></span>
<span data-ttu-id="eac22-171">*2016/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="eac22-171">*2016/architecture/description.txt*\\</span></span>
<span data-ttu-id="eac22-172">*2016/photo7.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="eac22-172">*2016/photo7.jpg*\\</span></span>

<span data-ttu-id="eac22-173">호출 하는 경우 `ListBlobs` 는 위의 샘플과 같이 컨테이너에서 계층적 목록이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="eac22-174">둘 다 포함 되어 있으면 `CloudBlobDirectory` 고 `CloudBlockBlob` 결과 출력은 다음과 유사 하 게 한 다음 컨테이너에 blob 및 디렉터리를 각각 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="eac22-175">선택적으로 설정할 수 있습니다 합니다 `UseFlatBlobListing` 의 매개 변수를 `ListBlobs` 메서드를 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="eac22-176">으로 컨테이너의 모든 blob는 반환 하는 경우에 `CloudBlockBlob` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="eac22-177">에 대 한 호출 `ListBlobs` 반환할 한 플랫 목록이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="eac22-178">및 컨테이너의 현재 내용에 따라 결과 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-178">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="eac22-179">Blob 다운로드</span><span class="sxs-lookup"><span data-stu-id="eac22-179">Download blobs</span></span>

<span data-ttu-id="eac22-180">Blob을 다운로드 하려면 먼저 blob 참조를 검색 한 다음 호출을 `DownloadToStream` 메서드.</span><span class="sxs-lookup"><span data-stu-id="eac22-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="eac22-181">다음 예제에서는 `DownloadToStream` 로컬 파일에 저장할 수 있습니다 하는 스트림 개체로 blob 콘텐츠를 전송 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="eac22-182">사용할 수도 있습니다는 `DownloadToStream` 메서드를 텍스트 문자열로 blob의 콘텐츠를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="eac22-183">Blob 삭제</span><span class="sxs-lookup"><span data-stu-id="eac22-183">Delete blobs</span></span>

<span data-ttu-id="eac22-184">Blob을 삭제 하려면 먼저 blob 참조를 가져온 및 호출 된 `Delete` 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="eac22-185">페이지에서 blob를 비동기적으로 나열</span><span class="sxs-lookup"><span data-stu-id="eac22-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="eac22-186">많은 수의 blob 나열 하는 경우 단일 목록 작업에서 반환 되는 결과의 수를 제어 하려면 결과 페이지에 blob를 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="eac22-187">이 예제는 큰 결과 집합이 반환 되기를 기다리는 동안 실행이 차단 되지 않도록 비동기적으로 페이지에 결과 반환 하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="eac22-188">이 예제에서는 플랫 blob 나열을 보여주지만 설정 하 여 계층적 나열을 수행할 수도 있습니다는 `useFlatBlobListing` 의 매개 변수를 `ListBlobsSegmentedAsync` 메서드를 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="eac22-189">샘플 정의 비동기 메서드를 사용 하는 `async` 블록.</span><span class="sxs-lookup"><span data-stu-id="eac22-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="eac22-190">``let!`` 키워드는 나열 작업이 완료 될 때까지 샘플 메서드의 실행을 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="eac22-191">이제이 비동기 루틴을 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="eac22-192">먼저 일부 더미 데이터 (이 자습서의 앞부분에서 만든 로컬 파일 사용)를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="eac22-193">이제는 루틴을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-193">Now, call the routine.</span></span> <span data-ttu-id="eac22-194">사용할 `Async.RunSynchronously` 비동기 작업을 실행 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="eac22-195">추가 blob에 쓰기</span><span class="sxs-lookup"><span data-stu-id="eac22-195">Writing to an append blob</span></span>

<span data-ttu-id="eac22-196">추가 blob은 로깅 등의 추가 작업을 위해 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="eac22-197">블록 blob과 같은 추가 blob은 블록으로 구성 되지만 추가 blob에 새 블록을 추가 하면 항상 blob 끝에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="eac22-198">업데이트 하거나 추가 blob의 기존 블록을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="eac22-199">추가 blob의 블록 Id는 블록 blob으로 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="eac22-200">추가 blob의 각 블록에는 최대 4MB까지 크기가 다양할 수 있습니다 및 추가 blob는 최대 50,000 개의 블록을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="eac22-201">추가 blob의 최대 크기 (4 X 50,000 개 블록) 보다 약간 더 195GB 되므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="eac22-202">다음 예제에서는 새 추가 blob을 만들고 간단한 로깅 작업을 시뮬레이션에 일부 데이터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="eac22-203">참조 [이해 블록 Blob, 페이지 Blob 및 추가 Blob](https://msdn.microsoft.com/library/azure/ee691964.aspx) 세 가지 blob 유형의 차이점에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="eac22-204">동시 액세스</span><span class="sxs-lookup"><span data-stu-id="eac22-204">Concurrent access</span></span>

<span data-ttu-id="eac22-205">여러 클라이언트 또는 여러 프로세스 인스턴스에서 blob에 대 한 동시 액세스를 지원, 사용할 수 있습니다 **Etag** 하거나 **임대**합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="eac22-206">**Etag** -blob 또는 컨테이너를 다른 프로세스에서 수정 되었다는 사실을 감지 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="eac22-207">**임대** -가져오는 단독, 갱신 가능, 쓰기 또는 특정 기간에 대 한 blob에 대 한 액세스를 삭제 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="eac22-208">자세한 내용은 [Microsoft Azure Storage에서 동시성 관리](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/)합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="eac22-209">명명 컨테이너</span><span class="sxs-lookup"><span data-stu-id="eac22-209">Naming containers</span></span>

<span data-ttu-id="eac22-210">Azure storage의 모든 blob 컨테이너에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="eac22-211">컨테이너는 blob 이름의 일부를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-211">The container forms part of the blob name.</span></span> <span data-ttu-id="eac22-212">예를 들어 `mydata` 이러한 샘플 blob Uri에서에서 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="eac22-213">컨테이너 이름에는 다음 명명 규칙을 따르는 유효한 DNS 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="eac22-214">컨테이너 이름은 문자 또는 숫자로 시작 해야 하며 문자, 숫자 및 대시 (-) 문자만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="eac22-215">모든 대시 (-) 문자 바로 앞뒤에 뒤에 문자 또는 숫자로; 컨테이너 이름에서 연속 대시 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="eac22-216">컨테이너 이름의 모든 문자는 소문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="eac22-217">컨테이너 이름은 3 ~ 63 자에서에서 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="eac22-218">참고 컨테이너의 이름을 항상 소문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="eac22-219">컨테이너 이름에는 대문자를 포함 하거나 컨테이너 명명 규칙 위반을 경우 400 오류 (잘못 된 요청)를 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="eac22-220">Blob에 대 한 보안 관리</span><span class="sxs-lookup"><span data-stu-id="eac22-220">Managing security for blobs</span></span>

<span data-ttu-id="eac22-221">기본적으로 Azure Storage 데이터 보안 유지를 계정 액세스 키를 보유 하는 계정 소유자에 대 한 액세스를 제한 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="eac22-222">저장소 계정의 blob 데이터를 공유 해야 할 경우 계정 액세스 키의 보안을 손상 시 키 지 않고도 중요 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="eac22-223">또한 Azure Storage에 연결을 통해 서 안전 하다는 것을 확인 하려면 blob 데이터를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="eac22-224">Blob 데이터에 대 한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-224">Controlling access to blob data</span></span>

<span data-ttu-id="eac22-225">기본적으로 저장소 계정의 blob 데이터는 저장소 계정 소유자만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="eac22-226">기본적으로 계정 액세스 키를 필요 Blob storage에 대 한 요청을 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="eac22-227">그러나 다음 다른 사용자에 게 특정 blob 데이터를 사용할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="eac22-228">Blob 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-228">Encrypting blob data</span></span>

<span data-ttu-id="eac22-229">Azure Storage 클라이언트와 서버에서 blob 데이터를 암호화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eac22-230">다음 단계</span><span class="sxs-lookup"><span data-stu-id="eac22-230">Next steps</span></span>

<span data-ttu-id="eac22-231">이제 Blob 저장소의 기본 사항을 배웠으므로 다음 링크를 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="eac22-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="eac22-232">도구</span><span class="sxs-lookup"><span data-stu-id="eac22-232">Tools</span></span>

- <span data-ttu-id="eac22-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span><span class="sxs-lookup"><span data-stu-id="eac22-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span></span>
<span data-ttu-id="eac22-234">F# Blob, 테이블 및 큐 Azure Storage 자산을 탐색 하 고 쉽게 CRUD 작업을 적용 하는 형식 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="eac22-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span><span class="sxs-lookup"><span data-stu-id="eac22-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span></span>
<span data-ttu-id="eac22-236">F# Microsoft Azure Table Storage 서비스를 사용 하 여 API</span><span class="sxs-lookup"><span data-stu-id="eac22-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="eac22-237">[Microsoft Azure Storage 탐색기 (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span><span class="sxs-lookup"><span data-stu-id="eac22-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span></span>
<span data-ttu-id="eac22-238">Windows, OS X 및 Linux에서 Azure Storage 데이터로 시각적으로 작업할 수 있도록 하는 Microsoft에서 무료로 사용할 수 있는 독립 실행형 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="eac22-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="eac22-239">Blob storage 참조</span><span class="sxs-lookup"><span data-stu-id="eac22-239">Blob storage reference</span></span>

- [<span data-ttu-id="eac22-240">.NET 용 azure Storage Api</span><span class="sxs-lookup"><span data-stu-id="eac22-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="eac22-241">Azure Storage 서비스 REST API 참조</span><span class="sxs-lookup"><span data-stu-id="eac22-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="eac22-242">관련된 지침</span><span class="sxs-lookup"><span data-stu-id="eac22-242">Related guides</span></span>

- [<span data-ttu-id="eac22-243">C#에서 Azure Blob Storage 시작</span><span class="sxs-lookup"><span data-stu-id="eac22-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="eac22-244">Windows에서 AzCopy 명령줄 유틸리티로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="eac22-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="eac22-245">Linux에서 AzCopy 명령줄 유틸리티로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="eac22-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="eac22-246">Azure Storage 연결 문자열 구성</span><span class="sxs-lookup"><span data-stu-id="eac22-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="eac22-247">Azure Storage 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="eac22-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="eac22-248">빠른 시작: .NET을 사용 하 여 개체 저장소에 blob를 만들려면</span><span class="sxs-lookup"><span data-stu-id="eac22-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
