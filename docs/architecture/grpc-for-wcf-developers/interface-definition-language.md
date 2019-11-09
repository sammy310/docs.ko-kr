---
title: 인터페이스 정의 언어-WCF 개발자를 위한 gRPC
description: 프로토콜 버퍼 IDL을 소개 합니다.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 00c73619c5c27003e200385d5f67d8b8b7546f9e
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841566"
---
# <a name="interface-definition-language"></a><span data-ttu-id="f394a-103">IDL(Interface Definition Language)</span><span class="sxs-lookup"><span data-stu-id="f394a-103">Interface Definition Language</span></span>

<span data-ttu-id="f394a-104">WCF를 사용 하는 경우 서비스는 런타임에 .NET 리플렉션을 사용 하 여 동적으로 생성 된 WSDL (웹 서비스 정의 언어)을 사용 하 여 설명 메타 데이터를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-104">With WCF, services can expose description metadata using the Web Service Definition Language (WSDL), which is generated dynamically using .NET Reflection at runtime.</span></span> <span data-ttu-id="f394a-105">개발자는이 메타 데이터를 사용 하 여 해당 서비스에 대 한 클라이언트를 생성할 수 있습니다 .이는 HTTP를 통한 SOAP와 같은 플랫폼 중립적인 바인딩이 사용 되는 경우에도 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-105">Developers can use this metadata to generate clients for those services, potentially in other languages if a platform-neutral binding such as SOAP over HTTP is used.</span></span>

<span data-ttu-id="f394a-106">gRPC는 프로토콜 버퍼의 IDL (Interface Definition Language)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-106">gRPC uses the Interface Definition Language (IDL) from Protocol Buffers.</span></span> <span data-ttu-id="f394a-107">프로토콜 버퍼 IDL은 개방형 사양을 사용 하는 사용자 지정 플랫폼 중립적인 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-107">The Protocol Buffers IDL is a custom, platform-neutral language with an open specification.</span></span> <span data-ttu-id="f394a-108">개발자는 `.proto` 파일을 코딩 하 여 서비스를 입력 및 출력과 함께 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-108">Developers hand-code `.proto` files to describe services along with their inputs and outputs.</span></span> <span data-ttu-id="f394a-109">이러한 `.proto` 파일을 사용 하 여 클라이언트 및 서버에 대 한 언어 또는 플랫폼별 스텁을 생성 하 여 여러 다른 플랫폼에서 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-109">These `.proto` files can then be used to generate language- or platform-specific stubs for clients and servers, allowing multiple different platforms to communicate.</span></span> <span data-ttu-id="f394a-110">팀은 `.proto` 파일을 공유 하 여 코드 종속성을 사용 하지 않고도 다른 사람의 서비스를 사용 하는 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-110">By sharing `.proto` files, teams can generate code to use each others' services without needing to take a code dependency.</span></span>

<span data-ttu-id="f394a-111">Protobuf IDL의 장점 중 하나는 사용자 지정 언어로, gRPC를 완전히 언어 및 플랫폼에 구애 받지 않고 다른 기술을 찾은 다음 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-111">One of the advantages of the Protobuf IDL is that as a custom language it enables gRPC to be completely language and platform agnostic, not favoring any technology over another.</span></span>

<span data-ttu-id="f394a-112">Protobuf IDL은 읽기 및 쓰기를 위한 것 이지만, WSDL은 컴퓨터에서 읽을 수 있는/쓰기 가능한 형식으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-112">The Protobuf IDL is also designed for humans to both read and write, whereas WSDL is intended as a machine-readable/writable format.</span></span> <span data-ttu-id="f394a-113">WCF 서비스의 WSDL을 변경 하려면 일반적으로 서비스 코드 자체를 변경 하 고 서비스를 실행 하 고 서버에서 WSDL 파일을 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-113">Changing the WSDL of a WCF service typically requires making the changes to the service code itself, running the service and regenerating the WSDL file from the server.</span></span> <span data-ttu-id="f394a-114">이와 대조적으로, `.proto` 파일을 사용 하면 텍스트 편집기를 사용 하 여 변경 내용을 적용 하 고 생성 된 코드를 통해 자동으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-114">By contrast, with a `.proto` file, changes are simple to apply with a text editor, and automatically flow through the generated code.</span></span> <span data-ttu-id="f394a-115">Visual Studio 2019은 파일을 저장할 때 백그라운드에서 `.proto` 파일을 빌드합니다. VS Code와 같은 다른 편집기를 사용 하는 경우 프로젝트를 빌드할 때 변경 내용이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-115">Visual Studio 2019 builds `.proto` files in the background when they are saved; when using other editors such as VS Code the changes will be applied when the project is built.</span></span>

<span data-ttu-id="f394a-116">XML 및 특히 SOAP와 비교할 때 Protobuf를 사용 하 여 인코드된 메시지는 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-116">When compared with XML, and particularly SOAP, messages encoded using Protobuf have many advantages.</span></span> <span data-ttu-id="f394a-117">Protobuf 메시지는 SOAP XML로 serialize 되는 것과 동일한 데이터 보다 작고 네트워크를 통해 인코딩, 디코딩 및 전송 하는 것이 더 빠를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-117">Protobuf messages tend to be smaller than the same data serialized as SOAP XML, and encoding, decoding and transmitting them over a network can be faster.</span></span>

<span data-ttu-id="f394a-118">SOAP와 비교할 때 Protobuf의 잠재적인 단점은 메시지가 사람이 읽을 수 없기 때문에 메시지 콘텐츠를 디버그 하는 데 추가 도구가 필요 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-118">The potential disadvantage of Protobuf compared to SOAP is that, because the messages are not human readable, additional tooling is required to debug message content.</span></span>

> [!TIP]
> <span data-ttu-id="f394a-119">gRPC는 미리 컴파일된 스텁을 사용 하지 않고 서비스에 동적으로 액세스 *하는 서버* 리플렉션을 지원 합니다. 단, 응용 프로그램 특정 클라이언트 보다 일반적인 용도의 도구를 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-119">gRPC *does* support server reflection for dynamically accessing services without pre-compiled stubs, although it is intended more for general-purpose tools than application-specific clients.</span></span> <span data-ttu-id="f394a-120">GRPC 서버 리플렉션에 대 한 자세한 내용은 GitHub의 [grpc/grpc](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) 리포지토리를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f394a-120">For more information about gRPC Server Reflection, see [grpc/grpc](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) repository on GitHub.</span></span>

> [!NOTE]
> <span data-ttu-id="f394a-121">NetTCP 바인딩과 함께 사용 되는 WCF의 이진 형식은 시 압축 성 및 성능 측면에서 Protobuf에 훨씬 더 가깝습니다. 그러나 NetTCP는 .NET 클라이언트와 서버 사이 에서만 사용할 수 있지만 Protobuf는 플랫폼 간 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="f394a-121">WCF's binary format, used with the NetTCP binding, is much closer to Protobuf in terms of compactness and performance, but NetTCP is only usable between .NET clients and servers, whereas Protobuf is a cross-platform solution.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f394a-122">[이전](approach.md)
>[다음](network-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="f394a-122">[Previous](approach.md)
[Next](network-protocols.md)</span></span>
