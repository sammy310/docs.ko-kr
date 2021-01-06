---
title: Wcf 개발자를 위한 gRPC gRPC와 WCF 비교
description: 분산 응용 프로그램을 빌드하기 위한 WCF 및 gRPC 프레임 워크의 비교입니다.
ms.date: 12/15/2020
ms.openlocfilehash: 7dd41c3d6f248bb1ef5eacb323b1443c7bc575a7
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938496"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="2cb5a-103">WCF와 gRPC 비교</span><span class="sxs-lookup"><span data-stu-id="2cb5a-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="2cb5a-104">이전 장은 Protobuf 및 gRPC가 메시지를 처리 하는 방식을 잘 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb5a-104">The previous chapter gave you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="2cb5a-105">Windows Communication Foundation (WCF)에서 gRPC로의 자세한 변환 작업을 수행 하기 전에 WCF에서 사용할 수 있는 기능이 gRPC에서 처리 되는 방식과 해당 하는 gRPC가 없는 경우 사용할 수 있는 해결 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb5a-105">Before you work through a detailed conversion from Windows Communication Foundation (WCF) to gRPC, it's important know how the features available in WCF are handled in gRPC and what workarounds you can use when there's no gRPC equivalent.</span></span> <span data-ttu-id="2cb5a-106">특히이 장에서는 다음 주제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="2cb5a-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="2cb5a-107">작업 및 메서드</span><span class="sxs-lookup"><span data-stu-id="2cb5a-107">Operations and methods</span></span>
- <span data-ttu-id="2cb5a-108">바인딩 및 전송</span><span class="sxs-lookup"><span data-stu-id="2cb5a-108">Bindings and transports</span></span>
- <span data-ttu-id="2cb5a-109">RPC 형식</span><span class="sxs-lookup"><span data-stu-id="2cb5a-109">RPC types</span></span>
- <span data-ttu-id="2cb5a-110">메타데이터</span><span class="sxs-lookup"><span data-stu-id="2cb5a-110">Metadata</span></span>
- <span data-ttu-id="2cb5a-111">오류 처리</span><span class="sxs-lookup"><span data-stu-id="2cb5a-111">Error handling</span></span>
- <span data-ttu-id="2cb5a-112">WS \* 프로토콜</span><span class="sxs-lookup"><span data-stu-id="2cb5a-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="2cb5a-113">gRPC 예제</span><span class="sxs-lookup"><span data-stu-id="2cb5a-113">gRPC example</span></span>

<span data-ttu-id="2cb5a-114">Visual Studio 2019 또는 명령줄에서 새 ASP.NET Core 5.0 gRPC 프로젝트를 만들 때 "Hello World"와 동일한 gRPC가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cb5a-114">When you create a new ASP.NET Core 5.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="2cb5a-115">`greeter.proto`서비스 및 해당 메시지를 정의 하는 파일과 `GreeterService.cs` 서비스 구현이 포함 된 파일로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb5a-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message that contains the user's name.
message HelloRequest {
  string name = 1;
}

// The response message that contains the greetings.
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

<span data-ttu-id="2cb5a-116">이 장은 gRPC의 다른 개념 및 기능을 설명 하는 경우이 예제 코드를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb5a-116">This chapter will refer to this example code when explaining different concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2cb5a-117">[이전](protobuf-maps.md)
>[다음](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="2cb5a-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
