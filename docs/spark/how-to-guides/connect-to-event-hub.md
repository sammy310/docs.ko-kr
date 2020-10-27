---
title: Azure Event Hubs에 .NET for Apache Spark 연결
description: 로컬 .NET for Apache Spark 인스턴스에서 Azure Event Hubs에 연결하는 방법을 알아봅니다.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: c8fd10992e63674032af4148e0673a5330d9086c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223960"
---
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a><span data-ttu-id="b5fa9-103">Azure Event Hubs에 .NET for Apache Spark 연결</span><span class="sxs-lookup"><span data-stu-id="b5fa9-103">Connect .NET for Apache Spark to Azure Event Hubs</span></span>

<span data-ttu-id="b5fa9-104">이 문서에서는 [.NET for Apache Spark](https://github.com/dotnet/spark) 애플리케이션을 Azure Event Hubs에 연결하여 Apache Kafka 스트림을 읽고 쓰는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-104">In this article, you will learn how to connect your [.NET for Apache Spark](https://github.com/dotnet/spark) application with Azure Event Hubs to read and write Apache Kafka streams.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5fa9-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b5fa9-105">Prerequisites</span></span>

<span data-ttu-id="b5fa9-106">이벤트 허브를 사용하여 Event Hubs 네임스페이스를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-106">Have an Event Hubs Namespace ready with an event hub.</span></span> <span data-ttu-id="b5fa9-107">단계별 가이드는 [빠른 시작: Azure Portal을 사용하여 이벤트 허브 만들기](/azure/event-hubs/event-hubs-create)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-107">For a step-by-step guide, refer to [Quickstart: Create an event hub using Azure portal](/azure/event-hubs/event-hubs-create).</span></span> <span data-ttu-id="b5fa9-108">Event Hubs 네임스페이스를 만드는 동안 표준 가격 책정 계층을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-108">Make sure to select the Standard Pricing tier while creating the Event Hub Namespace.</span></span>

## <a name="what-is-azure-event-hubs"></a><span data-ttu-id="b5fa9-109">Azure Event Hubs 정의</span><span class="sxs-lookup"><span data-stu-id="b5fa9-109">What is Azure Event Hubs</span></span>

<span data-ttu-id="b5fa9-110">[Azure Event Hubs](/azure/event-hubs/event-hubs-about)는 빅 데이터 스트리밍 플랫폼이자 이벤트 수집 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-110">[Azure Event Hubs](/azure/event-hubs/event-hubs-about) is a big-data streaming platform and event-ingestion service.</span></span> <span data-ttu-id="b5fa9-111">[Apache Kafka](https://kafka.apache.org/)와 쉽게 통합되어 고유한 클러스터를 관리, 구성 또는 실행하지 않고도 PaaS Kafka 환경을 제공할 수 있는 완전 관리형 PaaS(Platform as a Service)입니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-111">It is a fully managed Platform-as-a-Service (PaaS) that can easily integrate with [Apache Kafka](https://kafka.apache.org/) to give you the PaaS Kafka experience without having to manage, configure, or run your own clusters.</span></span>

## <a name="connect-your-application-to-azure-event-hubs"></a><span data-ttu-id="b5fa9-112">Azure Event Hubs에 애플리케이션 연결</span><span class="sxs-lookup"><span data-stu-id="b5fa9-112">Connect your application to Azure Event Hubs</span></span>

1. <span data-ttu-id="b5fa9-113">나중에 사용할 수 있도록 Event Hubs 연결 문자열 및 FQDN(정규화된 도메인 이름)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-113">Get the Event Hubs connection string and fully qualified domain name (FQDN) for later use.</span></span> <span data-ttu-id="b5fa9-114">자세한 지침은 [Event Hubs 연결 문자열 가져오기](/azure/event-hubs/event-hubs-get-connection-string)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-114">For instructions, see [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string).</span></span>
2. <span data-ttu-id="b5fa9-115">코드에서 네임스페이스의 세부 정보로 다음 구성을 설정하여 Kafka용 Event Hubs에서 읽기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-115">Set the following configurations with details from your namespace in your code to start reading from Event Hubs for Kafka:</span></span>
    1. <span data-ttu-id="b5fa9-116">애플리케이션에서 **BOOTSTRAP_SERVERS** 및 **EH_SASL** 을 다음과 같이 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-116">Update **BOOTSTRAP_SERVERS** and **EH_SASL** in your application like so:</span></span>

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a><span data-ttu-id="b5fa9-117">Azure Event Hubs 스트림에서 읽기</span><span class="sxs-lookup"><span data-stu-id="b5fa9-117">Read from Azure Event Hub stream</span></span>

<span data-ttu-id="b5fa9-118">이제 Kafka와 마찬가지로 Event Hubs를 사용하여 스트리밍을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-118">You can now start streaming with Event Hubs as you would with Kafka.</span></span> <span data-ttu-id="b5fa9-119">샘플 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-119">Sample code as shown below:</span></span>

```csharp
SparkSession spark = SparkSession
    .Builder()
    .AppName("Connect Event Hub")
    .GetOrCreate();

DataFrame df = spark
    .ReadStream()
    .Format("kafka")
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("subscribe", "spark-test")
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("kafka.request.timeout.ms", "60000")
    .Option("kafka.session.timeout.ms", "60000")
    .Option("failOnDataLoss", "false")
    .Load();

DataFrame dfWrite = df
    .WriteStream()
    .OutputMode("append")
    .Format("console")
    .Start();
```

## <a name="write-to-azure-event-hub-stream"></a><span data-ttu-id="b5fa9-120">Azure Event Hubs 스트림에 쓰기</span><span class="sxs-lookup"><span data-stu-id="b5fa9-120">Write to Azure Event Hub stream</span></span>

<span data-ttu-id="b5fa9-121">아래와 같이 동일한 방식으로 Event Hubs에 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-121">You can also write to Event Hubs in the same way, as shown below:</span></span>

```csharp
// df is the DataFrame to write

df.WriteStream()
    .Format("kafka")
    .Option("topic", topics)
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("checkpointLocation", "./checkpoint")
    .Start();
```

## <a name="run-your-application"></a><span data-ttu-id="b5fa9-122">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="b5fa9-122">Run your application</span></span>

<span data-ttu-id="b5fa9-123">.NET for Apache Spark 애플리케이션을 실행하려면 sbt 프로젝트의 `build.sbt`에 있는 `libraryDependency`를 사용하여 Spark 프로젝트 빌드 정의의 일부로 `spark-sql-kafka-0-10` 모듈을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-123">In order to run your .NET for Apache Spark application, define the `spark-sql-kafka-0-10` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="b5fa9-124">`spark-submit`(또는 `spark-shell`)와 같은 Spark 환경에서는 `--packages` 명령줄 옵션을 다음과 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-124">For Spark environments such as `spark-submit` (or `spark-shell`), use the `--packages` command-line option like so:</span></span>

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> <span data-ttu-id="b5fa9-125">실행하는 Spark 버전에 따라 패키지 버전을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5fa9-125">Make sure to include the package version in accordance with the version of Spark being run.</span></span>
