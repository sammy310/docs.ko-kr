---
title: F#을 사용하여 Azure Queue 스토리지 시작
description: Azure 큐는 애플리케이션 구성 요소 간에 안정적인 비동기 메시징을 제공합니다. 클라우드 메시징을 사용하면 애플리케이션 구성 요소를 독립적으로 조정할 수 있습니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 0b360348ce6966ce49a2ac0abd839844bdbe55f2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548366"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="bfac0-104">F #을 사용 하 여 Azure Queue storage 시작\#</span><span class="sxs-lookup"><span data-stu-id="bfac0-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="bfac0-105">Azure Queue Storage는 애플리케이션 구성 요소 간에 클라우드 메시징을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="bfac0-106">규모를 고려하여 애플리케이션을 디자인할 때는 애플리케이션 구성 요소를 개별적으로 확장할 수 있도록 각 구성 요소를 분리하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="bfac0-107">Queue Storage는 클라우드, 데스크톱, 온-프레미스 서버 또는 모바일 디바이스에서 실행 중인지와 관계 없이 애플리케이션 구성 요소 간에 통신을 위한 비동기 메시징을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="bfac0-108">Queue Storage는 또한 비동기 작업 관리와 프로세스 워크플로 작성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="bfac0-109">이 자습서 정보</span><span class="sxs-lookup"><span data-stu-id="bfac0-109">About this tutorial</span></span>

<span data-ttu-id="bfac0-110">이 자습서에서는 Azure Queue storage를 사용 하 여 몇 가지 일반적인 작업을 위해 F # 코드를 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="bfac0-111">큐 만들기 및 삭제, 큐 메시지 추가, 읽기 및 삭제 등의 작업을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="bfac0-112">큐 저장소에 대 한 개념적 개요는 [queue storage에 대 한 .net 가이드](/azure/storage/storage-dotnet-how-to-use-queues)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfac0-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfac0-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="bfac0-113">Prerequisites</span></span>

<span data-ttu-id="bfac0-114">이 가이드를 사용 하려면 먼저 [Azure storage 계정을 만들어야](/azure/storage/storage-create-storage-account)합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="bfac0-115">이 계정에 대 한 저장소 액세스 키도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="bfac0-116">F # 스크립트를 만들고 F# 대화형를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="bfac0-117">이 문서의 샘플은 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="bfac0-118">F # 스크립트를 만들려면 `.fsx` `queues.fsx` f # 개발 환경에서 확장명을 사용 하 여 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="bfac0-119">그런 다음 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 과 같은 [패키지 관리자](package-management.md) 를 사용 하 여 패키지를 설치 하 `WindowsAzure.Storage` 고 `WindowsAzure.Storage.dll` 지시어를 사용 하 여 스크립트에 참조 합니다 `#r` .</span><span class="sxs-lookup"><span data-stu-id="bfac0-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="bfac0-120">네임스페이스 선언 추가</span><span class="sxs-lookup"><span data-stu-id="bfac0-120">Add namespace declarations</span></span>

<span data-ttu-id="bfac0-121">`queues.fsx` 파일 맨 위에 다음 `open` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="bfac0-122">연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="bfac0-122">Get your connection string</span></span>

<span data-ttu-id="bfac0-123">이 자습서에 대 한 Azure Storage 연결 문자열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="bfac0-124">연결 문자열에 대 한 자세한 내용은 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfac0-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="bfac0-125">자습서의 경우 다음과 같이 스크립트에 연결 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="bfac0-126">그러나 실제 프로젝트에는이 방법이 **권장 되지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="bfac0-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="bfac0-127">스토리지 계정 키는 스토리지 계정의 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="bfac0-128">항상 스토리지 계정 키를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="bfac0-129">다른 사용자에게 배포하거나 하드 코딩하거나 다른 사람이 액세스할 수 있는 일반 텍스트 파일에 저장하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bfac0-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="bfac0-130">손상 된 것으로 생각 되는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="bfac0-131">실제 응용 프로그램의 경우 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="bfac0-132">구성 파일에서 연결 문자열을 가져오려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="bfac0-133">Azure 구성 관리자 사용은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="bfac0-134">.NET Framework의 형식과 같은 API를 사용할 수도 있습니다 `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="bfac0-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="bfac0-135">연결 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="bfac0-135">Parse the connection string</span></span>

<span data-ttu-id="bfac0-136">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="bfac0-137">그러면이 반환 됩니다 `CloudStorageAccount` .</span><span class="sxs-lookup"><span data-stu-id="bfac0-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="bfac0-138">큐 서비스 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="bfac0-138">Create the Queue service client</span></span>

<span data-ttu-id="bfac0-139">`CloudQueueClient`클래스를 사용 하면 Queue storage에 저장 된 큐를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="bfac0-140">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="bfac0-141">이제 데이터를 읽어 오고 Queue Storage에 데이터를 기록하는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="bfac0-142">큐 만들기</span><span class="sxs-lookup"><span data-stu-id="bfac0-142">Create a queue</span></span>

<span data-ttu-id="bfac0-143">이 예제에서는 큐가 없는 경우 큐를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="bfac0-144">큐에 메시지 삽입</span><span class="sxs-lookup"><span data-stu-id="bfac0-144">Insert a message into a queue</span></span>

<span data-ttu-id="bfac0-145">기존 큐에 메시지를 삽입 하려면 먼저 새를 만듭니다 `CloudQueueMessage` .</span><span class="sxs-lookup"><span data-stu-id="bfac0-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="bfac0-146">그런 다음 메서드를 호출 `AddMessage` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="bfac0-147">는 `CloudQueueMessage` 다음과 같이 문자열 (utf-8 형식) 또는 배열에서 만들 수 있습니다 `byte` .</span><span class="sxs-lookup"><span data-stu-id="bfac0-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="bfac0-148">다음 메시지 보기</span><span class="sxs-lookup"><span data-stu-id="bfac0-148">Peek at the next message</span></span>

<span data-ttu-id="bfac0-149">큐에서 메시지를 제거 하지 않고 메서드를 호출 하 여 큐의 맨 앞에 있는 메시지를 피킹할 수 있습니다 `PeekMessage` .</span><span class="sxs-lookup"><span data-stu-id="bfac0-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="bfac0-150">처리할 다음 메시지 가져오기</span><span class="sxs-lookup"><span data-stu-id="bfac0-150">Get the next message for processing</span></span>

<span data-ttu-id="bfac0-151">메서드를 호출 하 여 큐의 맨 앞에 있는 메시지를 검색 하 여 처리할 수 있습니다 `GetMessage` .</span><span class="sxs-lookup"><span data-stu-id="bfac0-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="bfac0-152">나중에를 사용 하 여 성공적으로 메시지 처리를 표시 `DeleteMessage` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="bfac0-153">대기 중인 메시지의 콘텐츠 변경</span><span class="sxs-lookup"><span data-stu-id="bfac0-153">Change the contents of a queued message</span></span>

<span data-ttu-id="bfac0-154">큐에서 검색 된 메시지의 콘텐츠를 즉시 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="bfac0-155">메시지가 작업을 나타내는 경우 이 기능을 사용하여 작업의 상태를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="bfac0-156">다음 코드는 큐 메시지를 새로운 콘텐츠로 업데이트하고 표시 제한 시간이 60초 더 늘어나도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="bfac0-157">그러면 메시지와 연결된 작업의 상태가 저장되고 클라이언트에서 메시지에 대한 작업을 계속할 수 있는 시간이 1분 더 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="bfac0-158">이 기술을 사용하여 처리 단계가 하드웨어 또는 소프트웨어 오류로 인해 실패하는 경우 처음부터 시작하지 않고도 큐 메시지에 대한 여러 단계의 워크플로를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="bfac0-159">일반적으로 다시 시도 수를 유지 하 고, 메시지를 몇 번 이상 다시 시도 하는 경우 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="bfac0-160">이 기능은 처리될 때마다 애플리케이션 오류를 트리거하는 메시지를 차단하여 보호해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="bfac0-161">큐에서 다음 메시지 제거</span><span class="sxs-lookup"><span data-stu-id="bfac0-161">De-queue the next message</span></span>

<span data-ttu-id="bfac0-162">다음 코드는 2단계를 거쳐 큐에서 메시지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="bfac0-163">를 호출 하면 `GetMessage` 큐에서 다음 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="bfac0-164">`GetMessage`에서 반환된 메시지는 이 큐의 메시지를 읽는 다른 코드에는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="bfac0-165">기본적으로, 이 메시지는 30초간 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="bfac0-166">큐에서 메시지 제거를 완료 하려면도 호출 해야 `DeleteMessage` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="bfac0-167">메시지를 제거하는 이 2단계 프로세스는 코드가 하드웨어 또는 소프트웨어 오류로 인해 메시지를 처리하지 못하는 경우 코드의 다른 인스턴스가 동일한 메시지를 가져와서 다시 시도할 수 있도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="bfac0-168">코드 `DeleteMessage` 는 메시지가 처리 된 직후에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="bfac0-169">공통 큐 저장소 Api와 함께 비동기 워크플로 사용</span><span class="sxs-lookup"><span data-stu-id="bfac0-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="bfac0-170">이 예제에서는 공통 큐 저장소 Api와 함께 비동기 워크플로를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="bfac0-171">큐에서 메시지를 제거하기 위한 추가적인 옵션</span><span class="sxs-lookup"><span data-stu-id="bfac0-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="bfac0-172">큐에서 메시지 검색을 사용자 지정할 수 있는 방법으로는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="bfac0-173">먼저, 메시지의 배치(최대 32개)를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="bfac0-174">두 번째로, 표시하지 않는 제한 시간을 더 길거나 더 짧게 설정하여 코드에서 각 메시지를 완전히 처리하는 시간을 늘리거나 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="bfac0-175">다음 코드 예제에서는 `GetMessages` 를 사용 하 여 한 번 호출에 20 개의 메시지를 가져온 다음 각 메시지를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="bfac0-176">또한 각 메시지에 대해 표시하지 않는 제한 시간을 5분으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="bfac0-177">5 분은 모든 메시지에 대해 동시에 시작 되므로,에 대 한 호출 이후로 5 분이 경과 된 후에는 `GetMessages` 삭제 되지 않은 모든 메시지가 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="bfac0-178">큐 길이 가져오기</span><span class="sxs-lookup"><span data-stu-id="bfac0-178">Get the queue length</span></span>

<span data-ttu-id="bfac0-179">큐에 있는 메시지의 추정된 개수를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="bfac0-180">`FetchAttributes`메서드는 메시지 수를 포함 하 여 큐 특성을 검색 하도록 큐 서비스에 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="bfac0-181">`ApproximateMessageCount`속성은 `FetchAttributes` 큐 서비스를 호출 하지 않고 메서드에서 검색 된 마지막 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="bfac0-182">큐 삭제</span><span class="sxs-lookup"><span data-stu-id="bfac0-182">Delete a queue</span></span>

<span data-ttu-id="bfac0-183">큐 및 해당 큐에 포함 된 모든 메시지를 삭제 하려면 `Delete` 큐 개체에서 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfac0-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="bfac0-184">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bfac0-184">Next steps</span></span>

<span data-ttu-id="bfac0-185">이제 Queue Storage의 기본 사항을 배웠으므로 다음 링크를 따라 좀 더 복잡한 스토리지 작업에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="bfac0-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="bfac0-186">.NET용 Azure Storage API</span><span class="sxs-lookup"><span data-stu-id="bfac0-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="bfac0-187">Azure Storage 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="bfac0-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="bfac0-188">Azure Storage 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="bfac0-188">Azure Storage Team Blog</span></span>](/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="bfac0-189">Azure Storage 연결 문자열 구성</span><span class="sxs-lookup"><span data-stu-id="bfac0-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="bfac0-190">Azure Storage 서비스 REST API 참조</span><span class="sxs-lookup"><span data-stu-id="bfac0-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
