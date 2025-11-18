# LyricsGenius MCP Server

A Model Context Protocol (MCP) server for accessing song lyrics and artist information from Genius.com via the LyricsGenius library.

## Features

- Search for artists and songs on Genius.com
- Get detailed information about artists
- Retrieve song lyrics
- Get artist albums and top songs
- Get album tracks
- Search across different content types (songs, artists, albums, etc.)

## Requirements

- Python 3.10+
- FastMCP 2.13.0+
- LyricsGenius API token (get one from https://genius.com/api-clients)

## Installation

1. Clone this repository
   ```bash
   git clone <repository-url>
   cd lyricsgenius-mcp-server
   ```

2. Install dependencies
   ```bash
   pip install -r requirements.txt
   ```

3. Set up your Genius API token
   - Create a `.env` file in the project root
   - Add your Genius API token:
     ```
     GENIUS_TOKEN=your_token_here
     ```

## Usage

### Running with FastMCP (Recommended)

FastMCP 2.13+ provides the modern way to run MCP servers:

```bash
# Run directly using fastmcp.json configuration
fastmcp run

# Or specify the server file explicitly
fastmcp run server.py
```

### Installing in Claude Desktop

```bash
fastmcp install claude-desktop
```

This will automatically configure Claude Desktop to use your server.

### Development Mode

```bash
fastmcp dev
```

### Running the server directly

```bash
python server.py
```

## Server Capabilities

### Tools

- `search(query, search_type=None, per_page=10, page=1)` - Search Genius for artists, songs, albums or other content
- `get_lyrics(title, artist=None)` - Get lyrics for a song directly
- `get_artist_songs(artist_identifier, per_page=20, sort="popularity")` - Get songs by an artist
- `get_artist_albums(artist_identifier)` - Get albums by an artist
- `get_album_tracks(album_identifier)` - Get tracks from an album by its ID or name

## License

MIT