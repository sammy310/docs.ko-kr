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
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a>Azure Event Hubs에 .NET for Apache Spark 연결

이 문서에서는 [.NET for Apache Spark](https://github.com/dotnet/spark) 애플리케이션을 Azure Event Hubs에 연결하여 Apache Kafka 스트림을 읽고 쓰는 방법을 알아봅니다.

## <a name="prerequisites"></a>필수 구성 요소

이벤트 허브를 사용하여 Event Hubs 네임스페이스를 준비합니다. 단계별 가이드는 [빠른 시작: Azure Portal을 사용하여 이벤트 허브 만들기](/azure/event-hubs/event-hubs-create)를 참조하세요. Event Hubs 네임스페이스를 만드는 동안 표준 가격 책정 계층을 선택해야 합니다.

## <a name="what-is-azure-event-hubs"></a>Azure Event Hubs 정의

[Azure Event Hubs](/azure/event-hubs/event-hubs-about)는 빅 데이터 스트리밍 플랫폼이자 이벤트 수집 서비스입니다. [Apache Kafka](https://kafka.apache.org/)와 쉽게 통합되어 고유한 클러스터를 관리, 구성 또는 실행하지 않고도 PaaS Kafka 환경을 제공할 수 있는 완전 관리형 PaaS(Platform as a Service)입니다.

## <a name="connect-your-application-to-azure-event-hubs"></a>Azure Event Hubs에 애플리케이션 연결

1. 나중에 사용할 수 있도록 Event Hubs 연결 문자열 및 FQDN(정규화된 도메인 이름)을 가져옵니다. 자세한 지침은 [Event Hubs 연결 문자열 가져오기](/azure/event-hubs/event-hubs-get-connection-string)를 참조하세요.
2. 코드에서 네임스페이스의 세부 정보로 다음 구성을 설정하여 Kafka용 Event Hubs에서 읽기를 시작합니다.
    1. 애플리케이션에서 **BOOTSTRAP_SERVERS** 및 **EH_SASL** 을 다음과 같이 업데이트합니다.

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a>Azure Event Hubs 스트림에서 읽기

이제 Kafka와 마찬가지로 Event Hubs를 사용하여 스트리밍을 시작할 수 있습니다. 샘플 코드는 다음과 같습니다.

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

## <a name="write-to-azure-event-hub-stream"></a>Azure Event Hubs 스트림에 쓰기

아래와 같이 동일한 방식으로 Event Hubs에 쓸 수도 있습니다.

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

## <a name="run-your-application"></a>애플리케이션 실행

.NET for Apache Spark 애플리케이션을 실행하려면 sbt 프로젝트의 `build.sbt`에 있는 `libraryDependency`를 사용하여 Spark 프로젝트 빌드 정의의 일부로 `spark-sql-kafka-0-10` 모듈을 정의합니다. `spark-submit`(또는 `spark-shell`)와 같은 Spark 환경에서는 `--packages` 명령줄 옵션을 다음과 같이 사용합니다.

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> 실행하는 Spark 버전에 따라 패키지 버전을 포함해야 합니다.
