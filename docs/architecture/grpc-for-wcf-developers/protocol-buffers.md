---
title: 프로토콜 버퍼-WCF 개발자를 위한 gRPC
description: GRPC 네트워킹에 사용 되는 프로토콜 버퍼 통신 형식을 소개 합니다.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 6b47c7f3576134d8ee44f79e329cc4879661e6c3
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841386"
---
# <a name="protocol-buffers"></a><span data-ttu-id="24a3e-103">프로토콜 버퍼</span><span class="sxs-lookup"><span data-stu-id="24a3e-103">Protocol buffers</span></span>

<span data-ttu-id="24a3e-104">gRPC 서비스는 WCF의 데이터 계약과 비슷하게 *Protobuf (프로토콜 버퍼) 메시지로*데이터를 보내고 받습니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to WCF's data contracts.</span></span> <span data-ttu-id="24a3e-105">Protobuf은 사용자가 읽을 수 있는 형식 (예: XML 또는 JSON)의 오버 헤드 없이 읽기 및 쓰기를 위해 컴퓨터의 구조화 된 데이터를 serialize 하는 효율적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="24a3e-106">이 장에서는 Protobuf가 작동 하는 방식과 고유한 Protobuf 메시지를 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="24a3e-107">Protobuf 작동 방식</span><span class="sxs-lookup"><span data-stu-id="24a3e-107">How Protobuf works</span></span>

<span data-ttu-id="24a3e-108">WCF의 데이터 계약을 비롯 한 대부분의 .NET 개체 serialization 기술은 런타임에 개체 구조를 분석 하기 위해 리플렉션을 사용 하 여 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at run time.</span></span> <span data-ttu-id="24a3e-109">이와 대조적으로 대부분의 Protobuf 라이브러리는 `.proto` 파일에서 전용 언어 (*프로토콜 버퍼 언어*)를 사용 하 여 앞에서 구조를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-109">By contrast, most Protobuf libraries require you to define the structure up front using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="24a3e-110">이 파일은 .NET, Java, C/C++, JavaScript 등을 비롯 하 여 지원 되는 플랫폼에 대 한 코드를 생성 하기 위해 컴파일러에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-110">This file is then used by a compiler to generate code for any of the supported platforms, including .NET, Java, C/C++, JavaScript, and many more.</span></span> <span data-ttu-id="24a3e-111">Protobuf 컴파일러 `protoc`는 대체 구현을 사용할 수 있지만 Google에서 유지 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-111">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="24a3e-112">생성 된 코드는 데이터의 빠른 serialization 및 deserialization을 위해 효율적이 고 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-112">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="24a3e-113">Protobuf 통신 형식 자체는 메시지를 나타내는 데 사용 되는 바이트 수를 최소화 하기 위해 몇 가지 뛰어난 트릭을 사용 하는 이진 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-113">The Protobuf wire format itself is a binary encoding, which uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="24a3e-114">이진 인코딩 형식에 대 한 정보는 Protobuf를 사용 하는 데 필요 하지 않지만 관심이 있는 경우 [프로토콜 버퍼 웹 사이트](https://developers.google.com/protocol-buffers/docs/encoding)에서 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24a3e-114">Knowledge of the binary encoding format isn't necessary to use Protobuf, but if you're interested you can learn more about it on [the Protocol Buffers web site](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="24a3e-115">[이전](why-grpc.md)
>[다음](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="24a3e-115">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
