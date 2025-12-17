package config

import (
	env "github.com/caarlos0/env/v11"
)

type Config struct {
	ExampleField string `env:"EXAMPLE_FIELD" envDefault:"default_value"`
}

func LoadConfig() (*Config, error) {
	cfg := &Config{}
	if err := env.Parse(cfg); err != nil {
		return nil, err
	}
	return cfg, nil
}
