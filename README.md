# ExFCM

Is a simple wrapper around Firebase Cloud Messaging that uses HTTPoison.

## Needed configuration

```elixir

config :exfcm,
  fcm_url: "https://fcm.googleapis.com/fcm/send"
  server_key: "yourKeyFromConsole"

```

## To send message to topic

```elixir
{:ok , result } = Message.put_data(%{"sample" => "true"})
    |> Message.put_notification("Github","is_awesome")
    |> Message.target_topic("aTopic")
    |> Message.send
```

## To send message to device or device group

```elixir
{:ok , result } = Message.put_data(%{"sample" => "true"})
    |> Message.put_notification("Github","is_awesome")
    |> Message.target_device("aTopic")
    |> Message.send
```

## Installation

If [available in Hex](https://hex.pm/packages/exfcm), the package can be installed as:

  1. Add `exfcm` to your list of dependencies in `mix.exs`:

    ```elixir
    def deps do
      [{:exfcm, "~> 0.1.0"}]
    end
    ```

  2. Ensure `exfcm` is started before your application:

    ```elixir
    def application do
      [applications: [:exfcm]]
    end
    ```
## TODO

* Add custom filters
* Add suport for additional params on notification
