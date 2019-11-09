---
title: Wcf 개발자를 위한 gRPC gRPC와 WCF 비교
description: 분산 응용 프로그램을 빌드하기 위한 WCF 및 gRPC 프레임 워크의 비교입니다.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5ab1380d4ded52abff08c35c430adf2f3ed7c58b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841296"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="a75c4-103">WCF와 gRPC 비교</span><span class="sxs-lookup"><span data-stu-id="a75c4-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="a75c4-104">이전 장은 Protobuf 및 gRPC가 메시지를 처리 하는 방식을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a75c4-104">The previous chapter should have given you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="a75c4-105">WCF에서 gRPC로의 자세한 변환 작업을 수행 하기 전에 현재 WCF에서 사용할 수 있는 기능의 범위가 gRPC에서 처리 되는 방식과 해당 하는 gRPC가 표시 되지 않는 경우 사용할 수 있는 해결 방법을 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a75c4-105">Before working through a detailed conversion from WCF to gRPC, it's important to look at how the range of features currently available in WCF are handled in gRPC and what workarounds you can use when there doesn't appear to be a gRPC equivalent.</span></span> <span data-ttu-id="a75c4-106">특히이 장에서는 다음 주제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="a75c4-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="a75c4-107">작업 및 메서드</span><span class="sxs-lookup"><span data-stu-id="a75c4-107">Operations and methods</span></span>
- <span data-ttu-id="a75c4-108">바인딩 및 전송</span><span class="sxs-lookup"><span data-stu-id="a75c4-108">Bindings and transports</span></span>
- <span data-ttu-id="a75c4-109">RPC 형식</span><span class="sxs-lookup"><span data-stu-id="a75c4-109">RPC types</span></span>
- <span data-ttu-id="a75c4-110">메타데이터</span><span class="sxs-lookup"><span data-stu-id="a75c4-110">Metadata</span></span>
- <span data-ttu-id="a75c4-111">오류 처리</span><span class="sxs-lookup"><span data-stu-id="a75c4-111">Error handling</span></span>
- <span data-ttu-id="a75c4-112">WS\* 프로토콜</span><span class="sxs-lookup"><span data-stu-id="a75c4-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="a75c4-113">gRPC 예제</span><span class="sxs-lookup"><span data-stu-id="a75c4-113">gRPC example</span></span>

<span data-ttu-id="a75c4-114">Visual Studio 2019 또는 명령줄에서 새 ASP.NET Core 3.0 gRPC 프로젝트를 만들 때 "Hello World"와 동일한 gRPC가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a75c4-114">When you create a new ASP.NET Core 3.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="a75c4-115">서비스 및 해당 메시지를 정의 하는 `greeter.proto` 파일과 서비스 구현이 포함 된 `GreeterService.cs` 파일로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a75c4-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message containing the user's name.
message HelloRequest {
  string name = 1;
}

// The response message containing the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

<span data-ttu-id="a75c4-116">이 장은 gRPC의 다양 한 개념 및 기능을 설명 하는 경우이 예제 코드를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a75c4-116">This chapter will refer to this example code when explaining various concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a75c4-117">[이전](protobuf-maps.md)
>[다음](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="a75c4-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
