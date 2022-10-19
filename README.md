import {Component} from 'react'
import './index.css'

class ColorApp extends Component {
  state = {isClicked: false}

  componentDidMount() {
    this.getColors()
  }

  getColors = async () => {
    const response = await fetch(
      'https://demo2965432.mockable.io/highon/colors',
    )
    const colors = await response.json()
    const {data} = colors
    console.log(data)
  }

  openCard = () => {
    this.setState({isClicked: true})
  }

  cancelBtn = () => {
    this.setState({isClicked: false})
  }

  render() {
    const {isClicked} = this.state
    return (
      <div className="color-app-container">
        <input type="search" className="user-input" />
        {isClicked ? (
          <div className="color-card">
            <div className="header-container">
              <p className="main-header">Create a color card</p>
            </div>
            <h1 className="title">Select the Color</h1>
            <ul>
              <button type="button" className="color1">
                .
              </button>
              <button type="button" className="color2">
                .
              </button>
              <button type="button" className="color3">
                .
              </button>
              <button type="button" className="color4">
                .
              </button>
              <button type="button" className="color5">
                .
              </button>
            </ul>
            <h1 className="sub-title">Give a title</h1>
            <button type="button" className="sub-title-btn">
              The Blue Carbuncle
            </button>
            <h1 className="description-title">Description</h1>
            <p className="description-des">
              Lorem Ipsum has been the industry standard dummy text ever since
              the 1500s, when an unknown printer took a galley of type and
              scrambled it to make a type
            </p>
            <div className="btn-container">
              <button type="button" className="save-btn">
                Save
              </button>
              <button
                type="button"
                className="cancel-btn"
                onClick={this.cancelBtn}
              >
                Cancel
              </button>
            </div>
          </div>
        ) : (
          <div>
            <button
              type="button"
              className="color-card-button"
              onClick={this.openCard}
            >
              <span>+</span> Create a Color Card
            </button>
          </div>
        )}
      </div>
    )
  }
}

export default ColorApp



.color-app-container {
  margin: 25px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.search-container {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.user-input {
  width: 500px;
  height: 35px;
  border-radius: 15px;
  outline: none;
  border: 1px solid #000;
  margin-bottom: 25px;
}
span {
  font-weight: bold;
  font-size: 28px;
  margin-right: 10px;
}
.color-card-button {
  width: 250px;
  height: 44px;
  outline: none;
  border: none;
  background-color: #757171;
  font-family: 'roboto';
  font-weight: 500;
  color: #fff;
  font-size: 18px;
  border-radius: 10px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}
.color-card {
  background-color: #757171;
  padding-left: 14px;
  padding-right: 14px;
  padding-bottom: 14px;
  width: 250px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.header-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-evenly;
  margin-top: 0;
  width: 250px;
  padding: 15px;
}
.multiply-icon {
  color: #fff;
  font-weight: 500;
  font-size: 18px;
  font-family: 'roboto';
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 0;
  align-self: flex-start;
  margin-left: 0;
}
.main-header {
  color: #fff;
  font-weight: 500;
  font-size: 16px;
  font-family: 'roboto';
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 0;
  text-align: center;
  align-self: center;
}
.title {
  font-family: 'roboto';
  font-size: 16px;
  font-weight: 400;
  color: #fffff6;
}
ul {
  padding-left: 0;
  list-style-type: none;
}
.color1 {
  background-color: #cd7f32;
  width: 25px;
  height: 13px;
  color: #cd7f32;
  outline: none;
  border: none;
  cursor: pointer;
  margin-right: 10px;
}
.color2 {
  background-color: #c8a2c8;
  width: 25px;
  height: 13px;
  color: #c8a2c8;
  outline: none;
  border: none;
  cursor: pointer;
  margin-right: 10px;
}
.color3 {
  background-color: #f8ed62;
  width: 25px;
  height: 13px;
  color: #f8ed62;
  outline: none;
  border: none;
  cursor: pointer;
  margin-right: 10px;
}
.color4 {
  background-color: #ff0000;
  width: 25px;
  height: 13px;
  color: #ff0000;
  outline: none;
  border: none;
  cursor: pointer;
  margin-right: 10px;
}
.color5 {
  background-color: #0033ff;
  width: 25px;
  height: 13px;
  color: #0033ff;
  outline: none;
  border: none;
  cursor: pointer;
}
.sub-title {
  font-family: 'roboto';
  font-size: 17px;
  font-weight: 500;
  color: #fffff6;
  margin-top: 0;
}
.sub-title-btn {
  width: 180px;
  height: 35px;
  outline: none;
  border: none;
  background-color: #a8a8a8;
  font-family: 'roboto';
  font-weight: 500;
  color: #fff;
  font-size: 14px;
  border-radius: 10px;
  cursor: pointer;
}
.description-title {
  font-family: 'roboto';
  font-weight: 500;
  color: #fff;
  font-size: 16px;
  margin-top: 10px;
}
.description-des {
  font-family: 'roboto';
  font-weight: 400;
  color: #fff;
  font-size: 14px;
  background-color: #a8a8a8;
  width: 220px;
  padding: 10px;
  border-radius: 8px;
  margin-top: 0;
  margin-bottom: 0;
}
.btn-container {
  margin-top: 15px;
}
.save-btn {
  width: 90px;
  height: 33px;
  outline: none;
  border: none;
  background-color: #fff;
  font-family: 'roboto';
  font-weight: 500;
  color: red;
  font-size: 14px;
  border-radius: 10px;
  cursor: pointer;
  margin: 10px;
}
.cancel-btn {
  width: 90px;
  height: 35px;
  outline: none;
  border: none;
  background-color: #fff;
  font-family: 'roboto';
  font-weight: 500;
  color: #000;
  font-size: 14px;
  border-radius: 10px;
  cursor: pointer;
  margin: 10px;
}
